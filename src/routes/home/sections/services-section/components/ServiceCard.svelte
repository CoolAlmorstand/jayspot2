<script>
  const {coverImage, text, title, gotoLocation } = $props()
  import { goto } from "$app/navigation";
</script>

<main class="md:border-1 border-gray-300 flex flex-col w-85 items-center justify-start rounded-2xl" >
  <img src={coverImage} class="md:max-w-60 w-6/10 mb-1 rounded-lg object-cover"/>
  <div class="text-center pt-3 flex flex-col items-center justify-center px-3">
    <p class="text-black font-semibold text-lg"> {title} </p>
    <p class="text-black font-light text-sm"> {text} </p>
    <button onclick={() => goto(gotoLocation)} class="font-medium texta-sm text-primary-500 p-1 px-2 rounded-lg border-0 border-[#7196DA] bga-[#7196DA]"> view details </button>
  </div>
</main>
