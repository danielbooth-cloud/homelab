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
      items: ['Grafana dashboards', 'Grafana Mimir metrics', 'Grafana Alloy collection', 'Loki log aggregation']
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
    'Coolify', 'Ghost', 'Dependency-Track', 'Locust', 'SonarQube', 
    'Kubechecks', 'Jira', 'Harbor', 'OAuth2-Proxy', 'Descheduler', 'Atlantis',
    'Chaos Mesh'
  ];
</script>

<div class="space-y-8">
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-pink)] text-[var(--color-palette-light)] p-8 rounded-3xl shadow-2xl transform hover:scale-[1.005] transition-all duration-500 relative overflow-hidden">
    <div class="absolute top-4 right-4 w-12 h-12 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-60"></div>
    <div class="absolute bottom-4 left-4 w-8 h-8 bg-[var(--color-palette-faded-pink)] rounded-full opacity-40"></div>
    <div class="relative z-10">
      <div class="mb-4">
        <h2 class="text-4xl font-black mb-2 tracking-tight">Supported Workloads & Services</h2>
        <div class="w-20 h-1 bg-[var(--color-palette-pink)] rounded-full"></div>
      </div>
      <p class="text-lg font-light leading-relaxed">Applications and services running on this homelab infrastructure</p>
    </div>
  </div>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    {#each workloads as workload, i}
      <div 
        class="bg-[var(--color-palette-faded-slate)] rounded-xl p-6 shadow-lg border border-[var(--color-palette-emerald)] transform hover:scale-[1.015] hover:shadow-xl transition-all duration-300 relative overflow-hidden group" 
        style="transition-delay: {i * 50}ms"
      >
        <div class="flex items-center gap-3 mb-4 relative z-10">
          {#if workload.icon}
            <div class="bg-[var(--color-palette-emerald)] text-[var(--color-palette-light)] p-2 rounded-lg shadow-md group-hover:scale-110 transition-transform duration-300">
              <svelte:component this={workload.icon} class="w-6 h-6" />
            </div>
          {/if}
          <h3 class="text-xl font-bold text-[var(--color-palette-light)] border-b border-[var(--color-palette-emerald)] pb-2">{workload.category}</h3>
        </div>
        <div class="space-y-2 relative z-10">
          {#each workload.items as item, j}
            <div 
              class="flex items-center gap-2 text-sm transform hover:translate-x-1 transition-transform duration-200" 
              style="transition-delay: {j * 30}ms"
            >
              <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full flex-shrink-0"></div>
              <span class="text-[var(--color-palette-light)]">{item}</span>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
  <div class="bg-[var(--color-palette-faded-purple)] border-3 border-[var(--color-palette-pink)] rounded-3xl p-10 shadow-2xl">
    <div class="flex items-center gap-4 mb-6">
      <div class="w-14 h-14 bg-[var(--color-palette-pink)] text-[var(--color-palette-light)] rounded-2xl flex items-center justify-center shadow-lg">
        <Server class="w-8 h-8" />
      </div>
      <div>
        <h3 class="text-2xl font-bold text-[var(--color-palette-pink)]">Service Availability</h3>
        <div class="w-16 h-0.5 bg-[var(--color-palette-pink)] mt-1"></div>
      </div>
    </div>
    <p class="text-[var(--color-palette-light)] mb-6 text-lg leading-relaxed">All services are deployed with high availability configurations and monitored 24/7 with automated alerts.</p>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <div class="bg-[var(--color-palette-faded-emerald)] p-6 rounded-2xl shadow-lg border border-[var(--color-palette-emerald)] border-l-3 border-[var(--color-palette-emerald)] transform hover:scale-[1.02] hover:shadow-xl transition-all duration-300 group">
        <h4 class="font-bold text-[var(--color-palette-emerald)] mb-3 text-lg flex items-center gap-2">
          <span>🔄</span> Kubernetes Workloads
        </h4>
        <p class="text-sm text-[var(--color-palette-light)] leading-relaxed">Deployed across multiple nodes with pod anti-affinity rules for resilience</p>
      </div>
      <div class="bg-[var(--color-palette-faded-pink)] p-6 rounded-2xl shadow-lg border border-[var(--color-palette-pink)] border-l-3 border-[var(--color-palette-pink)] transform hover:scale-[1.02] hover:shadow-xl transition-all duration-300 group">
        <h4 class="font-bold text-[var(--color-palette-pink)] mb-3 text-lg flex items-center gap-2">
          <span>💾</span> Data Services
        </h4>
        <p class="text-sm text-[var(--color-palette-light)] leading-relaxed">Replicated databases with automated backups and point-in-time recovery</p>
      </div>
    </div>
  </div>
  
  <!-- Hosted Services Section -->
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-faded-slate)] rounded-3xl p-10 shadow-2xl hover:border-[var(--color-palette-pink)] transition-all duration-500 relative overflow-hidden">
    <div class="absolute top-0 right-0 w-32 h-32 bg-[var(--color-palette-faded-pink)] rounded-full -translate-y-16 translate-x-16 opacity-20"></div>
    <div class="relative z-10">
      <div class="flex items-center gap-4 mb-6">
        <div class="w-14 h-14 bg-[var(--color-palette-pink)] text-[var(--color-palette-light)] rounded-2xl flex items-center justify-center shadow-lg">
          <Globe class="w-8 h-8" />
        </div>
        <div>
          <h3 class="text-2xl font-bold text-[var(--color-palette-pink)]">Hosted Services</h3>
          <div class="w-16 h-0.5 bg-[var(--color-palette-pink)] mt-1"></div>
          <p class="text-[var(--color-palette-light)] mt-2">{hostedServices.length}+ self-hosted applications running in the homelab</p>
        </div>
      </div>
      
      <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 xl:grid-cols-8 gap-4">
        {#each hostedServices as service, i}
          <div 
            class="bg-[var(--color-palette-faded-slate)] p-4 rounded-lg shadow-md border border-[var(--color-palette-pink)] transform hover:scale-105 hover:shadow-lg hover:border-[var(--color-palette-emerald)] transition-all duration-300 group cursor-pointer"
            style="transition-delay: {i * 25}ms"
          >
            <div class="flex items-center justify-center h-12 relative z-10">
              <span class="text-sm font-semibold text-[var(--color-palette-light)] text-center group-hover:text-[var(--color-palette-emerald)] transition-colors duration-300">{service}</span>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>