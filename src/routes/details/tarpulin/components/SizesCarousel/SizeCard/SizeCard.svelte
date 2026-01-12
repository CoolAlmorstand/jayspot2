

<script lang="ts">

  import SizesDropDown from "./components/SizesDropDown.svelte";
  import GoodForCard from "./components/GoodForCard.svelte";

  const { bannerImage, size }: {
    size: "Small" | "Medium" | "Large",
    bannerImage: string
  } = $props()
  
  const shortDescription = {
    Small: "For Personal events and small business signage needs",
    Medium: "Perfect For Standard displays and storefronts",
    Large: "Perfect For Maximum impact and visibility"
  }
</script>


<div class="p-2 flex flex-col items-center rounded-lg border-1 shadow-[0_0_5px_rgba(0,0,0,0.6)] w-full">
  <div class="border-b-2 border-text-500/20 w-full flex flex-row gap-2 ">
    <img class="rounded-lg w-3/5" src={bannerImage}>
    <div class="flex flex-col">
      <p class="text-text-500 text-lg font-medium"> {size} </p>
      <p class="text-text-400 "> {shortDescription[size]}</p>
    </div> 
  </div>
  
  <div class="gap-3 px-2 pt-1 w-full flex flex-row items-start">
   
    <SizesDropDown />

    <div class="mb-5 px-3 bg-primary-600 rounded">
      <p class="text-text-100 font-medium"> ₱ 200 </p>
    </div>
  </div>

  <GoodForCard size={size} />
  <button class="bg-primary-600 px-3 rounded font-semibold text-text-50 py-1"> Order Now ₱ 200 </button>
</div>
