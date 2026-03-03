


<script lang="ts">
  import { writable, type Writable } from "svelte/store";
  import { onMount } from "svelte"
  import loadingBoxGif from "$lib/assets/loading-boxes.gif"

  const sampleImages = Array.from( Object.values(import.meta.glob("$lib/assets/tarpulin-samples/*", {as: "URL", eager: true} ) ), (item) => item.default )
  const imagesReference: Element[] = []

  const loadedImages = writable<(null | HTMLImageElement)[]>([])

  console.log(sampleImages)
  let gallaryContainer: HTMLElement;

  onMount( async () => {
    const observer = new IntersectionObserver( async (entries, observer) => {
      entries.forEach( async (entry) => {
        if(entry.isIntersecting) {
          const index = imagesReference.indexOf(entry.target);
          const imageUrl = sampleImages[index] 
          loadedImages.update((array) => {
            array[index] = new Image() 
            array[index].src = imageUrl
            return array
          }) 
        }
      })
    })
    imagesReference.forEach(image => observer.observe(image) )
  })
</script>


<div bind:this={gallaryContainer} class="w-9/10 bg-red-200 h-80 flex flex-col overflow-y-auto gap-2">
  {#each sampleImages as imageUrlPromise, i}
    <div bind:this={imagesReference[i]} class="flex-shrink-0 w-30 h-30 bg-blue-200">
      {#if $loadedImages[i]}
        <img src={$loadedImages[i]} />
      {:else}
        <img src={loadingBoxGif} />
      {/if}
    </div>
  {/each}
</div>

