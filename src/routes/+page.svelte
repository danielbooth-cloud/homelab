<script>
  import { 
    ChevronRight, Home, Cloud, Wrench, ShoppingCart, Monitor, 
    Database, Network, GitBranch, Settings, Zap, Server, Gauge 
  } from '@lucide/svelte';
  import OverviewSection from './OverviewSection.svelte';
  import ArchitectureSection from './ArchitectureSection.svelte';
  import TechStackSection from './TechStackSection.svelte';
  import WorkloadsSection from './WorkloadsSection.svelte';
  import PartsSection from './PartsSection.svelte';

  let activeSection = $state('overview');

  const navigation = [
    { id: 'overview', label: 'Overview', icon: Home },
    { id: 'architecture', label: 'Architecture', icon: Server },
    { id: 'techstack', label: 'Tech Stack', icon: Monitor },
    { id: 'workloads', label: 'Workloads', icon: Wrench },
    { id: 'parts', label: 'Parts List', icon: ShoppingCart }
  ];
</script>

<div class="min-h-screen" style="background-color: var(--color-palette-dark);">
  <div class="flex">
    <!-- Sidebar -->
    <div class="w-64 shadow-xl min-h-screen relative z-10 border-r-2 border-[var(--color-palette-emerald)]" style="background-color: var(--color-palette-faded-slate);">

      
      <div class="p-6 border-r border-(--color-palette-faded-emerald) bg-(--color-palette-dark)">
        <div class="flex items-center gap-3">
          <div class="bg-(--color-palette-pink) text-(--color-palette-light) p-2 rounded-lg shadow-lg">
            <h1 class="text-xl font-bold">🏠</h1>
          </div>
          <div>
            <h1 class="text-xl font-bold text-(--color-palette-pink)">Homelab</h1>
            <p class="text-sm text-(--color-palette-light)">Daniel's Homelab</p>
          </div>
        </div>
      </div>
      
      <nav class="p-4 space-y-2">
        {#each navigation as item}
          <button
            onclick={() => { activeSection = item.id }}
            class="w-full flex items-center gap-3 px-4 py-3 rounded-lg transition-all duration-200 text-left"
            style="{
              activeSection === item.id
                ? 'background-color: var(--color-palette-pink); color: var(--color-palette-light); box-shadow: 0 4px 6px -1px var(--color-palette-dark), 0 2px 4px -2px var(--color-palette-dark); transform: translateX(0.25rem);'
                : 'color: var(--color-palette-light); background-color: var(--color-palette-faded-dark); border: 2px solid var(--color-palette-pink);'
            }"
          >
            {#if item.icon}
              <item.icon class="w-4 h-4 {
                activeSection === item.id ? 'animate-pulse' : ''
              }" />
            {/if}
            <span>{item.label}</span>
          </button>
        {/each}
      </nav>
      
      <!-- Decorative circles below navigation -->
      <div class="relative p-4 mt-95">
        <div class="absolute top-2 left-8 w-12 h-12 bg-[var(--color-palette-emerald)] rounded-full opacity-30 group-hover:bg-[var(--color-palette-pink)] transition-colors duration-300"></div>
        <div class="absolute top-8 right-6 w-8 h-8 bg-[var(--color-palette-pink)] rounded-full opacity-40 animate-pulse"></div>
        <div class="absolute top-16 left-16 w-6 h-6 bg-[var(--color-palette-emerald)] rounded-full opacity-50 group-hover:bg-[var(--color-palette-pink)] transition-colors duration-300"></div>
        <div class="absolute top-20 right-12 w-10 h-10 bg-[var(--color-palette-pink)] rounded-full opacity-35 group-hover:bg-[var(--color-palette-emerald)] transition-colors duration-300"></div>
        <div class="absolute top-28 left-6 w-4 h-4 bg-[var(--color-palette-emerald)] rounded-full opacity-60 animate-pulse"></div>
      </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 p-8">
      {#if activeSection === 'overview'}
        <OverviewSection />
      {:else if activeSection === 'architecture'}
        <ArchitectureSection />
      {:else if activeSection === 'techstack'}
        <TechStackSection />
      {:else if activeSection === 'workloads'}
        <WorkloadsSection />
      {:else if activeSection === 'parts'}
        <PartsSection />
      {/if}
    </div>
  </div>
</div>
