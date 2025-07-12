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
    'AdGuard', 'Chatbox AI', 'Bitwarden', 'DPaste', 'Homepage', 'LanguageTool', 
    'LinkAce', 'Maybe', 'Minecraft', 'Nextcloud', 'Outline', 'OwnCloud', 
    'Reactive Resume', 'Ghost', 'Dependency-Track', 'Locust', 'SonarQube', 
    'Kubechecks', 'Jira', 'Harbor', 'OAuth2-Proxy', 'Descheduler', 'Atlantis',
    'Chaos Mesh'
  ];
</script>

<div class="space-y-8">
  <div class="bg-(--color-palette-emerald) text-(--color-palette-light) p-8 rounded-2xl shadow-xl relative overflow-hidden">
    <div class="relative z-10">
      <h2 class="text-4xl font-extrabold mb-2 drop-shadow-md">Supported Workloads & Services</h2>
      <p class="text-lg">Applications and services running on this homelab infrastructure</p>
    </div>
  </div>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    {#each workloads as workload, i}
      <div 
        class="bg-(--color-palette-light) rounded-xl p-6 shadow-lg border border-(--color-palette-emerald) transform hover:scale-[1.03] hover:shadow-xl transition-all duration-300 relative overflow-hidden group" 
        style="transition-delay: {i * 50}ms"
      >
        <div class="flex items-center gap-3 mb-4 relative z-10">
          {#if workload.icon}
            <div class="bg-(--color-palette-pink) text-(--color-palette-light) p-2 rounded-lg shadow-md">
              <svelte:component this={workload.icon} class="w-6 h-6" />
            </div>
          {/if}
          <h3 class="text-xl font-bold text-(--color-palette-emerald)">{workload.category}</h3>
        </div>
        <div class="space-y-2 relative z-10">
          {#each workload.items as item, j}
            <div 
              class="flex items-center gap-2 text-sm transform hover:translate-x-1 transition-transform duration-200" 
              style="transition-delay: {j * 30}ms"
            >
              <Zap class="w-3 h-3 text-(--color-palette-emerald)" />
              <span class="text-(--color-palette-emerald)">{item}</span>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
  <div class="bg-(--color-palette-light) p-6 rounded-xl shadow-lg border border-(--color-palette-emerald)">
    <div class="flex items-center gap-3 mb-4">
      <div class="bg-(--color-palette-pink) text-(--color-palette-light) p-2 rounded-lg shadow-md">
        <Server class="w-5 h-5" />
      </div>
      <h3 class="text-xl font-bold text-(--color-palette-emerald)">Service Availability</h3>
    </div>
    <p class="text-(--color-palette-emerald) mb-4">All services are deployed with high availability configurations and monitored 24/7 with automated alerts.</p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
      <div class="bg-(--color-palette-faded-emerald) p-4 rounded-xl shadow-md border border-(--color-palette-emerald) transform hover:scale-[1.02] transition-all duration-200">
        <h4 class="font-bold text-(--color-palette-emerald) mb-2">Kubernetes Workloads</h4>
        <p class="text-sm text-(--color-palette-emerald)">Deployed across multiple nodes with pod anti-affinity rules for resilience</p>
      </div>
      <div class="bg-(--color-palette-faded-pink) p-4 rounded-xl shadow-md border border-(--color-palette-pink) transform hover:scale-[1.02] transition-all duration-200">
        <h4 class="font-bold text-(--color-palette-pink) mb-2">Data Services</h4>
        <p class="text-sm text-(--color-palette-emerald)">Replicated databases with automated backups and point-in-time recovery</p>
      </div>
    </div>
  </div>
  
  <!-- Replace the Enhanced Hosted Services Section with this simpler version -->
  <div class="bg-(--color-palette-light) p-8 rounded-xl shadow-lg border border-(--color-palette-emerald) relative overflow-hidden">
    
    <div class="relative z-10">
      <div class="flex items-center gap-4 mb-6">
        <div class="bg-(--color-palette-emerald) text-(--color-palette-light) p-3 rounded-xl shadow-lg">
          <Globe class="w-8 h-8" />
        </div>
        <div>
          <h3 class="text-3xl font-bold text-(--color-palette-emerald)">Hosted Services</h3>
          <p class="text-(--color-palette-emerald) mt-1">{hostedServices.length}+ self-hosted applications running in the homelab</p>
        </div>
      </div>
      
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 xl:grid-cols-8 gap-4">
        {#each hostedServices as service, i}
          <div 
            class="bg-(--color-palette-light) p-4 rounded-lg shadow-md border border-(--color-palette-emerald) transform hover:scale-105 hover:shadow-lg transition-all duration-300 group cursor-pointer"
            style="transition-delay: {i * 25}ms"
          >
            
            <div class="flex items-center justify-center h-12 relative z-10">
              <span class="text-sm font-semibold text-(--color-palette-emerald) text-center group-hover:text-(--color-palette-pink) transition-colors duration-300">{service}</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>