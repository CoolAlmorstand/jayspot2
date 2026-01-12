

<script lang="ts">
  import printerImage from "$lib/assets/5.png"
  import SizesCarousel from "./components/SizesCarousel/SizesCarousel.svelte";
  import SampleGallary from "./components/SampleGallary/SampleGallary.svelte";
  import WhyChooseUsCard from "./components/WhyChooseUsCard.svelte";

</script>


<div class="w-screen flex flex-col items-center pt-3">
  <div class="mb-10 flex flex-col items-center w-full"> 
    <img class="rounded max-w-8/10" src={printerImage} />
    <p class="font-medium text-xl text-text-900"> Tarpulin Printing </p>
    <p class="ml-[2px] text-text-500"> High Quality, Fast Services, Affordable Prices </p> 
  </div>
  

  <div class="gap-5 flex flex-col items-center py-2 w-full">
    <SizesCarousel />
    <SampleGallary />
    <WhyChooseUsCard />
  </div>
</div>
