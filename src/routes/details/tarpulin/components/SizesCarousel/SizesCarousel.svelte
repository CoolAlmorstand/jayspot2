
<script lang="ts">
  import * as Carousel from "$lib/components/ui/carousel/index.js";
  import SizeCard from "./SizeCard/SizeCard.svelte";
  import type { CarouselAPI } from "$lib/components/ui/carousel/context.js";
  import Autoplay from "embla-carousel-autoplay";

  import bannerImageSmall from "$lib/assets/23.png"
  import bannerImageMedium from "$lib/assets/24.png"
  import bannerImageBig from "$lib/assets/25.png"

  const sizes = ["Small", "Medium", "Large"]

  let api = $state<CarouselAPI>();
 
  const count = $derived(api ? api.scrollSnapList().length : 0);
  let current = $state(0);

  $effect(() => {
    if (api) {
      current = api.selectedScrollSnap();
      api.on("select", () => {
        current = api!.selectedScrollSnap()
      });
    }
  });

  const plugin = Autoplay({ delay: 2000, stopOnInteraction: true });

  function scrollViaButton(direction: "next" | "prev") {
    if(direction == "next") {
      api?.scrollNext()
    }
    else if(direction == "prev") {
      api?.scrollPrev()
    }
    plugin.stop()
  }
</script>

<div class="flex flex-col items-center w-full">
  <p class="text-lg text-text-500 font-medium mb-1 -mt-3"> Sizes </p>
  <Carousel.Root plugins={[plugin]} setApi={(emblaApi) => (api = emblaApi)} opts={{loop: true}} class="mb-3 w-10/10">
    <Carousel.Content class="px-3 py-1"> 
      <Carousel.Item class="basis-1/1" >
        <SizeCard size="Small" bannerImage={bannerImageSmall}/>
      </Carousel.Item>

      <Carousel.Item class="basis-1/1" >
        <SizeCard size="Medium" bannerImage={bannerImageMedium}/>
      </Carousel.Item>

      <Carousel.Item class="basis-1/1" >
        <SizeCard size="Large" bannerImage={bannerImageBig}/>
      </Carousel.Item>

    </Carousel.Content>
  </Carousel.Root>
  
  <div class="items-center gap-3 flex flex-row justify-center w-full">
    <i onclick={() => scrollViaButton("prev")} class="text-xl fa-solid fa-circle-arrow-left"></i>
    <div class="h-7 max-w-3/5 px-7 rounded-lg shadow-[0_0_5px_rgba(0,0,0,0.6)] flex flex-row justify-center items-center">
      <p class="text-text-500 font-medium"> {sizes[current]} </p>
    </div>

    <i onclick={() => scrollViaButton("next")} class="text-xl fa-solid fa-circle-arrow-right"></i>
  </div>
</div>
