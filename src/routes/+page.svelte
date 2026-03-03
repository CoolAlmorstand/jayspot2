<script>
  import { onMount } from 'svelte';

  let visible = false;

  onMount(() => {
    setTimeout(() => (visible = true), 50);
  });
</script>

<svelte:head>
  <link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;700;800&family=DM+Sans:wght@300;400&display=swap" rel="stylesheet" />
</svelte:head>

<main class="min-h-screen bg-[#0a0a0f] flex items-center justify-center px-6 py-10 overflow-hidden relative">

  <!-- Ambient glow -->
  <div class="pointer-events-none fixed top-0 left-1/2 -translate-x-1/2 w-[600px] h-[600px] rounded-full"
    style="background: radial-gradient(circle, rgba(255,77,77,0.08) 0%, transparent 70%);">
  </div>

  <!-- Card -->
  <div
    class="relative bg-[#111118] border border-[#1e1e2e] rounded-2xl p-10 max-w-md w-full text-center transition-all duration-700 ease-out"
    class:opacity-0={!visible}
    class:translate-y-6={!visible}
    class:opacity-100={visible}
    class:translate-y-0={visible}
  >

    <!-- Top accent line -->
    <div class="absolute top-0 left-[10%] right-[10%] h-px"
      style="background: linear-gradient(90deg, transparent, #ff4d4d, transparent);">
    </div>

    <!-- Globe icon -->
    <div class="mx-auto mb-7 w-[72px] h-[72px] rounded-full flex items-center justify-center border border-[rgba(255,77,77,0.25)] animate-pulse-glow"
      style="background: linear-gradient(135deg, rgba(255,77,77,0.15), rgba(255,140,66,0.1));">
      <svg class="w-8 h-8 text-[#ff4d4d]" viewBox="0 0 24 24" fill="none" stroke="currentColor"
        stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
        <circle cx="12" cy="12" r="10"/>
        <line x1="2" y1="2" x2="22" y2="22"/>
        <path d="M12 2a15.3 15.3 0 0 1 4 10"/>
        <path d="M8 21.5A15.3 15.3 0 0 1 8 12"/>
        <path d="M2 12h5"/>
        <path d="M17 12h5"/>
      </svg>
    </div>

    <!-- Badge -->
    <span class="inline-block text-[#ff4d4d] bg-[rgba(255,77,77,0.1)] border border-[rgba(255,77,77,0.25)] text-[0.65rem] font-bold tracking-[0.18em] uppercase px-3 py-1 rounded-full mb-4"
      style="font-family: 'Syne', sans-serif;">
      Access Restricted
    </span>

    <!-- Heading -->
    <h1 class="text-[#e8e8f0] text-3xl font-extrabold leading-tight tracking-tight mb-4"
      style="font-family: 'Syne', sans-serif;">
      Not Available<br/>in Your Region
    </h1>

    <!-- Description -->
    <p class="text-[#6b6b80] text-sm leading-relaxed mb-8" style="font-family: 'DM Sans', sans-serif;">
      This content is unavailable in your location due to regional licensing We're sorry for the inconvenience.
    </p>

    <!-- Divider -->
    <div class="h-px bg-[#1e1e2e] mb-7"></div>

    <!-- Meta -->
    <div class="flex justify-center gap-8 flex-wrap">
      {#each [['Error Code', 'GEO_451'], ['Status', 'Blocked'], ['Reason', 'Region Lock']] as [label, value]}
        <div class="flex flex-col items-center gap-1">
          <span class="text-[#6b6b80] text-[0.65rem] uppercase tracking-widest" style="font-family: 'DM Sans', sans-serif;">{label}</span>
          <span class="text-[#e8e8f0] text-sm font-bold" style="font-family: 'Syne', sans-serif;">{value}</span>
        </div>
      {/each}
    </div>

    <!-- Back button -->
    <a href="/"
      class="inline-block mt-8 px-8 py-3 rounded-xl text-sm font-bold tracking-wide text-[#6b6b80] bg-[rgba(255,255,255,0.04)] border border-[#1e1e2e] hover:bg-[rgba(255,255,255,0.08)] hover:text-[#e8e8f0] hover:border-[rgba(255,255,255,0.15)] transition-all duration-200"
      style="font-family: 'Syne', sans-serif;">
      ← Go Back
    </a>

  </div>
</main>

<style>
  @keyframes pulse-glow {
    0%, 100% { box-shadow: 0 0 0 0 rgba(255, 77, 77, 0.15); }
    50%       { box-shadow: 0 0 0 14px rgba(255, 77, 77, 0); }
  }

  .animate-pulse-glow {
    animation: pulse-glow 3s ease-in-out infinite;
  }
</style>
