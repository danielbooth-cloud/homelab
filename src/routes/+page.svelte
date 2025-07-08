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

<div class="min-h-screen bg-gradient-to-br from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800">
  <div class="flex">
    <!-- Sidebar -->
    <div class="w-64 bg-white/90 dark:bg-gray-800/90 backdrop-blur-sm shadow-xl min-h-screen border-r border-gray-200/50 dark:border-gray-700/50 relative z-10">
      <div class="p-6 border-b border-gray-200/50 dark:border-gray-700/50 bg-gradient-to-r from-blue-50 to-indigo-50 dark:from-blue-900/20 dark:to-indigo-900/20">
        <div class="flex items-center gap-3">
          <div class="bg-gradient-to-br from-blue-500 to-indigo-600 text-white p-2 rounded-lg shadow-lg">
            <h1 class="text-xl font-bold">🏠</h1>
          </div>
          <div>
            <h1 class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-indigo-600 dark:from-blue-400 dark:to-indigo-400">Homelab</h1>
            <p class="text-sm text-gray-600 dark:text-gray-400">Daniel's Homelab</p>
          </div>
        </div>
      </div>
      
      <nav class="p-4 space-y-2">
        {#each navigation as item}
          <button
            onclick={() => { activeSection = item.id }}
            class="w-full flex items-center gap-3 px-4 py-3 rounded-lg transition-all duration-200 text-left {
              activeSection === item.id
                ? 'bg-gradient-to-r from-blue-600 to-indigo-600 text-white shadow-md translate-x-1'
                : 'text-gray-700 dark:text-gray-300 hover:bg-gray-100 dark:hover:bg-gray-700/50 hover:translate-x-1'
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