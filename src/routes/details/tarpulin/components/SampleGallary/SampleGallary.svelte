

<script lang="ts">
  import { writable, type Writable } from "svelte/store";
  import { onMount } from "svelte"
  import loadingBoxGif from "$lib/assets/loading-boxes.gif"

  const sampleImages = Object.values( import.meta.glob("$lib/assets/tarpulin-samples/*", {as: "URL"} ) )
  const loadedImages: Writable<(null | string)[]> = writable( Array.from({length: Object.keys(sampleImages).length}, () => null) )

  const imagesReference: Element[] = []

  let gallaryContainer: HTMLElement;

  onMount( async () => {
    const observer = new IntersectionObserver( async (entries, observer) => {
      entries.forEach( async (entry) => {
        if(entry.isIntersecting) {
          const index = imagesReference.indexOf(entry.target);
          const image = await sampleImages[index]()
          loadedImages.update((array) => {
            array[index] = image.default  
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

