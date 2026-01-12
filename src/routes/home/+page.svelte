

<script lang="ts">
  import HeroSection from "./sections/HeroSection.svelte";
  import ServicesSection from "./sections/services-section/ServicesSection.svelte";
  import { scrollIntoView } from "$lib/utils"
  import type { SvelteComponent } from "svelte";

  let servicesSection: HTMLElement;
</script>

<main class="flex flex-col items-center pt-10">
  <HeroSection viewServices={() => scrollIntoView(servicesSection)}/>

  <section bind:this={servicesSection} >
    <ServicesSection/>
  </section>
</main>
