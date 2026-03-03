<script lang="ts">
	import './layout.css';
	import '../app.css';
	import favicon from '$lib/assets/favicon.svg';
  import '@fortawesome/fontawesome-free/css/all.min.css';

  import Header from '$lib/components/layouts/Header.svelte';
	let { children } = $props();
</script>

<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<div class="flex flex-col h-screen w-screen">
  {@render children()}
</div>
