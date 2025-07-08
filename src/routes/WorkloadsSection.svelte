<script lang="ts">
  import { Zap, Server, Monitor, Cloud, Database, Gauge, GitBranch, Globe } from '@lucide/svelte';
  type Workload = {
    category: string;
    icon: typeof Server;
    items: string[];
  };
  const workloads: Workload[] = [
    {
      category: 'Container Platform',
      icon: Monitor,
      items: ['Kubernetes (Talos Linux)', 'Container Registry', 'Helm Charts', 'GitOps (ArgoCD)']
    },
    {
      category: 'Virtualization',
      icon: Cloud,
      items: ['Apache CloudStack', '20-30 Production VMs', 'Development environments', 'Linux VMs only']
    },
    {
      category: 'AI/ML & LLM',
      icon: Zap,
      items: ['DeepSeek R1 models', 'Llama 3.1/3.2 inference', 'Ollama platform', 'Computer vision workloads']
    },
    {
      category: 'Data Services',
      icon: Database,
      items: ['Longhorn Replicas', 'MongoDB', 'Redis caching', 'Time-series databases']
    },
    {
      category: 'Monitoring & Observability',
      icon: Gauge,
      items: ['Grafana Mimir metrics', 'Grafana Alloy collection', 'Grafana dashboards', 'Loki log aggregation']
    },
    {
      category: 'Development & CI/CD',
      icon: GitBranch,
      items: ['ArgoCD GitOps', 'GitHub Actions runners', 'Terraform', 'Atmos', 'Helmfile']
    }
  ];

  const hostedServices = [
    'AdGuard', 'Affine', 'Bitwarden', 'DPaste', 'Homepage', 'LanguageTool', 
    'LinkAce', 'Maybe', 'Minecraft', 'Nextcloud', 'Outline', 'OwnCloud', 
    'Reactive Resume', 'Ghost', 'Dependency-Track', 'Locust', 'SonarQube', 
    'Kubechecks', 'Jira', 'Harbor', 'OAuth2-Proxy', 'Descheduler', 'Atlantis',
    'Chaos Mesh'
  ];
</script>

<div class="space-y-8">
  <div class="bg-gradient-to-r from-purple-600 via-fuchsia-600 to-pink-600 text-white p-8 rounded-2xl shadow-xl relative overflow-hidden">
    <div class="absolute top-0 left-0 w-full h-full bg-white/5 backdrop-blur-sm opacity-20 z-0"></div>
    <div class="absolute -top-24 -right-24 w-64 h-64 bg-white/10 rounded-full blur-3xl"></div>
    <div class="relative z-10">
      <h2 class="text-4xl font-extrabold mb-2 drop-shadow-md">Supported Workloads & Services</h2>
      <p class="text-lg opacity-90">Applications and services running on this homelab infrastructure</p>
    </div>
  </div>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    {#each workloads as workload, i}
      <div 
        class="bg-gradient-to-br from-white to-gray-50 dark:from-gray-800 dark:to-gray-900 rounded-xl p-6 shadow-lg border border-gray-200/50 dark:border-gray-700/50 backdrop-blur-sm transform hover:scale-[1.03] hover:shadow-xl transition-all duration-300 relative overflow-hidden group" 
        style="transition-delay: {i * 50}ms"
      >
        <div class="absolute inset-0 bg-purple-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-purple-500/10 rounded-full blur-2xl group-hover:bg-purple-500/20 transition-colors duration-300"></div>
        <div class="flex items-center gap-3 mb-4 relative z-10">
          {#if workload.icon}
            <div class="bg-gradient-to-br from-purple-500 to-fuchsia-600 text-white p-2 rounded-lg shadow-md">
              <svelte:component this={workload.icon} class="w-6 h-6" />
            </div>
          {/if}
          <h3 class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-purple-700 to-fuchsia-700 dark:from-purple-300 dark:to-fuchsia-300">{workload.category}</h3>
        </div>
        <div class="space-y-2 relative z-10">
          {#each workload.items as item, j}
            <div 
              class="flex items-center gap-2 text-sm transform hover:translate-x-1 transition-transform duration-200" 
              style="transition-delay: {j * 30}ms"
            >
              <Zap class="w-3 h-3 text-purple-500" />
              <span class="text-gray-700 dark:text-gray-300">{item}</span>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
  <div class="bg-white/80 dark:bg-gray-800/80 p-6 rounded-xl shadow-lg border border-gray-200/50 dark:border-gray-700/50 backdrop-blur-sm">
    <div class="flex items-center gap-3 mb-4">
      <div class="bg-gradient-to-br from-purple-500 to-fuchsia-600 text-white p-2 rounded-lg shadow-md">
        <Server class="w-5 h-5" />
      </div>
      <h3 class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-purple-700 to-fuchsia-700 dark:from-purple-300 dark:to-fuchsia-300">Service Availability</h3>
    </div>
    <p class="text-gray-700 dark:text-gray-300 mb-4">All services are deployed with high availability configurations and monitored 24/7 with automated alerts.</p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div class="bg-gradient-to-br from-purple-50 to-fuchsia-50 dark:from-purple-900/30 dark:to-fuchsia-900/30 p-4 rounded-xl shadow-md border border-purple-200/50 dark:border-purple-700/50 transform hover:scale-[1.02] transition-all duration-200">
        <h4 class="font-bold text-purple-800 dark:text-purple-300 mb-2">Kubernetes Workloads</h4>
        <p class="text-sm text-gray-600 dark:text-gray-400">Deployed across multiple nodes with pod anti-affinity rules for resilience</p>
      </div>
      <div class="bg-gradient-to-br from-fuchsia-50 to-pink-50 dark:from-fuchsia-900/30 dark:to-pink-900/30 p-4 rounded-xl shadow-md border border-fuchsia-200/50 dark:border-fuchsia-700/50 transform hover:scale-[1.02] transition-all duration-200">
        <h4 class="font-bold text-fuchsia-800 dark:text-fuchsia-300 mb-2">Data Services</h4>
        <p class="text-sm text-gray-600 dark:text-gray-400">Replicated databases with automated backups and point-in-time recovery</p>
      </div>
    </div>
  </div>
  
  <!-- Replace the Enhanced Hosted Services Section with this simpler version -->
  <div class="bg-gradient-to-br from-white to-gray-50 dark:from-gray-800 dark:to-gray-900 p-8 rounded-xl shadow-lg border border-gray-200/50 dark:border-gray-700/50 backdrop-blur-sm relative overflow-hidden">
    <div class="absolute inset-0 bg-gradient-to-r from-purple-500/5 via-fuchsia-500/5 to-pink-500/5 opacity-50"></div>
    <div class="absolute -top-32 -right-32 w-64 h-64 bg-purple-500/10 rounded-full blur-3xl"></div>
    <div class="absolute -bottom-32 -left-32 w-64 h-64 bg-fuchsia-500/10 rounded-full blur-3xl"></div>
    
    <div class="relative z-10">
      <div class="flex items-center gap-4 mb-6">
        <div class="bg-gradient-to-br from-purple-500 to-fuchsia-600 text-white p-3 rounded-xl shadow-lg">
          <Globe class="w-8 h-8" />
        </div>
        <div>
          <h3 class="text-3xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-purple-700 to-fuchsia-700 dark:from-purple-300 dark:to-fuchsia-300">Hosted Services</h3>
          <p class="text-gray-600 dark:text-gray-400 mt-1">{hostedServices.length}+ self-hosted applications running in the homelab</p>
        </div>
      </div>
      
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 xl:grid-cols-8 gap-4">
        {#each hostedServices as service, i}
          <div 
            class="bg-white/60 dark:bg-gray-700/60 backdrop-blur-sm p-4 rounded-lg shadow-md border border-gray-200/30 dark:border-gray-600/30 transform hover:scale-105 hover:shadow-lg transition-all duration-300 group cursor-pointer"
            style="transition-delay: {i * 25}ms"
          >
            <div class="absolute inset-0 bg-gradient-to-br from-purple-500/10 to-fuchsia-500/10 opacity-0 group-hover:opacity-100 transition-opacity duration-300 rounded-lg"></div>
            <div class="flex items-center justify-center h-12 relative z-10">
              <span class="text-sm font-semibold text-gray-700 dark:text-gray-300 text-center group-hover:text-purple-700 dark:group-hover:text-purple-300 transition-colors duration-300">{service}</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>