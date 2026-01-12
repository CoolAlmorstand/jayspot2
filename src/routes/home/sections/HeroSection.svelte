

<script lang="ts">
  import shopBackground from "$lib/assets/3.png"
  
  const { viewServices }: {
    viewServices: () => any;
  } = $props()
</script>

<main class="md:flex-row md:items-center mb-30 w-full flex flex-col items-center">
  <img class="md:max-w-2/4" src={shopBackground} />
    <div class="flex flex-col justify-end">
      <div class="md:text-left md:mb-5 text-center mb-30 w-full px-2">
        <p class="mb-1 text-2xl font-medium"> Unleash Your Creativity With Our Print Quality </p>
        <p class="text-sm "> High Quality, Fast Sevices, Affordable Prices</p>
      </div>

      <div class="md:px-2 mt-20 px-7 w-full flex flex-row justify-start items-center">
        <button onclick={viewServices} class="flex flex-row justify-center items-center gap-1 text-white font-semibold p-2 bg-primary-500 rounded-lg " > 
          View Our Services 
        </button> 
      </div>
    </div>
</main>
