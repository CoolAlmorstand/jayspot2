

<script lang="ts">
  import Button from "$lib/components/ui/button/button.svelte";
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js"
</script>



<DropdownMenu.Root> 
  <DropdownMenu.Trigger > 
    {#snippet child({props}) }
      <button {...props} class="font-medium flex flex-row gap-1 items-center pl-2 pr-1 rounded bg-black text-text-100 "> 3 x 5 <i class="fa-solid fa-chevron-down"></i> </button> 
    {/snippet}
  </DropdownMenu.Trigger>

  <DropdownMenu.Content class="ml-8 w-60 bg-text-800 text-text-100 maxh-h-80"> 
    <DropdownMenu.Label> Choose Size </DropdownMenu.Label>
    <DropdownMenu.Group class="flex flex-row"> 
      <div class="flex flex-col w-1/2">
        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>


        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>

        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>
      </div>
      
      <div class="flex flex-col w-1/2">
        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>


        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>

        <DropdownMenu.Item> 
          <button class="w-full font-semibold bg-text-100 text-text-800 rounded px-3"> 8 x 7 </button>
        </DropdownMenu.Item>
      </div>

    </DropdownMenu.Group>
  </DropdownMenu.Content>
</DropdownMenu.Root>
