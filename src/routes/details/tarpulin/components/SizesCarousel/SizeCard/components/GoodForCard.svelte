
<script lang="ts">
  
  const { size } : {
    size: "Small" | "Medium" | "Large"
  } = $props()

  const bulletPoints = {
    Small: [
      "Vertical pole banners for street lighting and event venues",
      "Hanging banners for trade show booths and retail displays",
      "Narrow directional signs and wayfinding markers"
    ],
    Medium: [
      "Storefront window promotions and seasonal sale banners",
      "Restaurant patio menus and outdoor seating area signage",
      "Yard signs for real estate, political campaigns, and services"
    ],
    Large: [
      "Stage backdrops for performances, presentations",
      "Roadside billboard-style advertising for high visibility",
      "Event entrance archways and welcome banners for festivals"
    ]
  }
</script>



<div class="flex flex-col gap-3 px-3 w-full pt-2 pb-5 rounded-xl ">
  <p class="text-text-500 font-semibold"> Good For </p>

    {#each bulletPoints[size] as bulletPoint}
      <div class="gap-2 text-text-500 pl-2 rounded-lg flex items-start flex-row w-full"> 
        <i class="flex-shrink-0 text-text-800 text-xs mt-1 fa-solid fa-circle"></i>
        <p class="text-sm"> {bulletPoint} </p>
      </div>
    {/each} 
</div>


