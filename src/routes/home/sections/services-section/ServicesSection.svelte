

<script>

  import ServiceCard from "./components/ServiceCard.svelte"

  import printerImage from "$lib/assets/4.png"
  import tarpolinPrinterImage from "$lib/assets/5.png"
  import shirtPrintingImage from "$lib/assets/9.png"
  import idImage from "$lib/assets/1.png"
  import mugPrintingImage from "$lib/assets/10(6).png"
  import tatooImage from "$lib/assets/15.png"
  import onlineServicesImage from "$lib/assets/16.png"

</script>

<main class="lg:gap-20 md:flex-row md:justify-center flex-wrap px-2 pt-5 pb-20 gap-10 w-full flex flex-col items-stretch">
  <ServiceCard 
    coverImage={printerImage} 
    title="Printing, Flyers, Cards, Documents, ETC" 
    text="High Quality Colored Print Xeros/Photo Copy, Stickers, Calling Cards, Key Chains, Awards"
    gotoLocation="/details/tarpulin"
  /> 
  <ServiceCard 
    coverImage={tarpolinPrinterImage} 
    title="Tarpulin Printing" 
    text="Enhance Your Message With Our Vibrant High Resolution Tarpolins!"
    gotoLocation="/details/tarpulin"
  /> 
  <ServiceCard 
    coverImage={shirtPrintingImage} 
    title="T-Shirt Printing" 
    text="Make Your Dream Shirt Come To Life!" 
  />
  <ServiceCard 
    coverImage={onlineServicesImage} 
    title="Online Services" 
    text="Pay Bills, Write Reports, Encode, Reseach Inquiries, Anything You Need" 
  />
  <ServiceCard 
    coverImage={idImage} 
    title="Rush Id" 
    text="Get High Quality Id Pictures In Under 2 Minutes!"
  /> 
  <ServiceCard 
    coverImage={mugPrintingImage} 
    title="Mug Printing" 
    text="Print Your Favorite Desigs In Your Favorite Cups!" 
  />
  <ServiceCard 
    coverImage={tatooImage} 
    title="Tatoo Artist" 
    text="Get Your Tatoo At Jays Spot By Our Profesional Tatoo Artist" 
  />
</main>
