<script lang="ts">
  import { Home, Cloud, Server, Database, Network, Settings, Zap, Gauge, Monitor } from '@lucide/svelte';
  export const architectureData = {
    homeInfra: [
      {
        name: 'AMD EPYC Server',
        icon: Server,
        status: 'Core',
        details: 'Primary compute server running all workloads',
        specs: {
          'CPU': 'EPYC 7302P (16c/32t)',
          'RAM': '128GB ECC',
          'Storage': '1TB NVMe x2',
          'GPU': 'RTX 4060 Ti 16GB'
        }
      },
      {
        name: 'Beelink ME Mini NAS',
        icon: Database,
        status: 'Storage',
        details: 'Network attached storage for backups and files',
        specs: {
          'Drives': '2TB NVME x2',
          'Config': 'RAID 1 (4TB usable)',
          'Noise': '~19dB ultra-quiet'
        }
      },
      {
        name: 'GL-MT6000 (Flint 2)',
        icon: Network,
        status: 'Network',
        details: 'Primary router and Tailscale subnet gateway',
        specs: {
          'WAN': 'ISP connection',
          'LAN': '192.168.1.0/24',
          'VPN': 'Tailscale gateway'
        }
      },
      {
        name: 'HP t640 Thin Client',
        icon: Monitor,
        status: 'Access',
        details: 'RDP access device for virtualized workloads',
        specs: {
          'CPU': 'AMD Ryzen R1505G',
          'RAM': '8GB DDR4',
          'Storage': '32GB eMMC',
          'Displays': 'Dual 4K support'
        }
      }
    ],
    cloudServices: [
      {
        name: 'Kamaji Control Plane',
        icon: Settings,
        status: 'K8s Management',
        details: 'Manages homelab Kubernetes control planes',
        specs: {
          'Features': 'Multi-tenant K8s',
          'Use': 'Homelab control plane hosting'
        }
      },
      {
        name: 'Zitadel Identity Provider',
        icon: Settings,
        status: 'Identity',
        details: 'Centralized authentication and authorization',
        specs: {
          'Auth': 'OIDC/SAML/OAuth2',
          'MFA': 'TOTP/WebAuthn'
        }
      },
      {
        name: 'HashiCorp Vault',
        icon: Database,
        status: 'Secrets',
        details: 'Centralized secrets and certificate management',
        specs: {
          'Features': 'PKI, Dynamic secrets',
          'Integration': 'K8s External Secrets Operator'
        }
      },
      {
        name: 'Redis Cache',
        icon: Zap,
        status: 'Cache',
        details: 'Session storage and IaC state coordination',
        specs: {
          'Persistence': 'RDB + AOF',
          'Use': 'Atmos state, sessions',
        }
      },
      {
        name: 'Uptime Kuma',
        icon: Gauge,
        status: 'Monitoring',
        details: 'Status page and uptime monitoring',
        specs: {
          'Features': 'HTTP/HTTPS/TCP checks',
          'Notifications': 'Slack/Discord/Email'
        }
      }
    ]
  };
</script>

<div class="space-y-8">
  <div class="bg-gradient-to-r from-indigo-600 via-blue-600 to-cyan-600 text-white p-8 rounded-2xl shadow-xl relative overflow-hidden">
    <div class="absolute top-0 left-0 w-full h-full bg-white/5 backdrop-blur-sm opacity-20 z-0"></div>
    <div class="absolute -top-24 -right-24 w-64 h-64 bg-white/10 rounded-full blur-3xl"></div>
    <div class="relative z-10">
      <h2 class="text-4xl font-extrabold mb-2 drop-shadow-md">Hybrid Cloud Architecture</h2>
      <p class="text-lg opacity-90">Enterprise-grade components powering my homelab environment</p>
    </div>
  </div>
  
  <!-- Enhanced Architecture Diagram -->
  <div class="flex justify-center">
    <!-- Explanation Text Box -->
    <div class="bg-white/90 dark:bg-gray-800/90 rounded-2xl p-8 shadow-lg border border-blue-200/50 dark:border-blue-600/50 max-w-9xl w-full transform hover:scale-[1.01] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-blue-500/10 rounded-full blur-2xl group-hover:bg-blue-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-4 relative z-10">
        <div class="bg-gradient-to-br from-blue-500 to-indigo-600 text-white p-2 rounded-lg shadow-lg transform group-hover:scale-110 transition-transform duration-300">
          <span class="text-lg">💡</span>
        </div>
        <h3 class="text-xl font-bold text-blue-900 dark:text-blue-100">Architecture Overview</h3>
      </div>
      <div class="space-y-4 text-gray-700 dark:text-gray-300 relative z-10">
        <p class="text-base leading-relaxed">
          This diagram illustrates the <strong>hybrid cloud Kubernetes architecture</strong> that leverages both on-premises homelab infrastructure and Oracle Cloud Infrastructure (OCI) to create a cost-effective, enterprise-grade solution.
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div class="bg-blue-50/80 dark:bg-blue-900/30 p-4 rounded-xl border-l-4 border-blue-400 hover:border-l-6 transform hover:scale-[1.02] hover:shadow-lg transition-all duration-300">
            <h4 class="font-semibold text-blue-800 dark:text-blue-200 mb-2">🏠 Homelab Cluster</h4>
            <p class="text-sm">Runs Kubernetes worker nodes on Talos Linux, providing compute resources for workloads while keeping infrastructure costs minimal.</p>
          </div>
          <div class="bg-green-50/80 dark:bg-green-900/30 p-4 rounded-xl border-l-4 border-green-400 hover:border-l-6 transform hover:scale-[1.02] hover:shadow-lg transition-all duration-300">
            <h4 class="font-semibold text-green-800 dark:text-green-200 mb-2">☁️ OCI ARM Cluster</h4>
            <p class="text-sm">Hosts the Kubernetes control plane using Kamaji, leveraging Oracle's free tier ARM instances for zero-cost cluster management.</p>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="flex justify-center mt-12">
    <div class="bg-gray-200 dark:bg-gray-300 rounded-3xl p-10 border border-gray-400/50 dark:border-gray-500/50 max-w-7xl w-full flex flex-col items-center relative transform hover:scale-[1.01] transition-all duration-300 group">
      <!-- Animated Tailscale network border with glow/pulse -->
      <div class="absolute -inset-1 border-4 border-dashed border-blue-950/90 rounded-2xl animate-pulse opacity-70 group-hover:opacity-90 transition-opacity duration-300"></div>
      
      <div class="flex flex-col items-center mb-10 relative z-10">
        <img src="https://tailscale.com/favicon.ico" alt="Tailscale" class="w-20 h-20 mb-3 transform group-hover:scale-110 transition-transform duration-300" />
        <h2 class="text-3xl font-bold text-gray-800 dark:text-gray-900">Tailscale VPN Overlay Network</h2>
      </div>
      <div class="flex flex-col md:flex-row gap-24 w-full justify-center relative z-10"> <!-- gap-24 for more space -->
        <div class="flex-1 bg-white rounded-2xl border border-blue-300 p-10 flex flex-col items-center shadow-lg min-w-[320px] max-w-[400px] transform hover:scale-[1.03] hover:shadow-xl transition-all duration-300 relative overflow-hidden group/box">
          <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover/box:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-blue-500/10 rounded-full blur-2xl group-hover/box:bg-blue-500/20 transition-colors duration-300"></div>
          <span class="text-xl font-semibold text-blue-700 mb-4 relative z-10">🏠 Homelab Cluster</span>
          <img src="https://upload.wikimedia.org/wikipedia/commons/3/39/Kubernetes_logo_without_workmark.svg" alt="Kubernetes" class="w-20 h-20 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <img src="https://cdn.worldvectorlogo.com/logos/apache-cloudstack.svg" alt="Cloudstack" class="w-14 h-14 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR-GgQtIeLgHjsD7DPY7Hs93vNI-dp9Vrvzqg&s" alt="Talos" class="w-16 h-16 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <span class="text-orange-600 font-medium text-lg relative z-10">Talos Worker Nodes</span>
        </div>
        
        <!-- SVG line positioned between the boxes -->
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 group-hover:scale-110 transition-transform duration-300 z-20" style="width: 120px; height: 4px; margin-top: 20px;">
          <svg width="120" height="4" style="position: absolute; top: 0; left: 0;">
            <line x1="0" y1="2" x2="120" y2="2" stroke="#1e40af" stroke-width="4" stroke-dasharray="16 8" stroke-linecap="round">
              <animate attributeName="stroke-dashoffset" from="-24" to="0" dur="1s" repeatCount="indefinite" />
            </line>
          </svg>
        </div>
        
        <div class="flex-1 bg-white rounded-2xl border border-blue-300 p-10 flex flex-col items-center shadow-lg min-w-[320px] max-w-[400px] transform hover:scale-[1.03] hover:shadow-xl transition-all duration-300 relative overflow-hidden group/box">
          <div class="absolute inset-0 bg-green-500/5 opacity-0 group-hover/box:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-green-500/10 rounded-full blur-2xl group-hover/box:bg-green-500/20 transition-colors duration-300"></div>
          <span class="text-xl font-semibold text-blue-700 mb-4 relative z-10">☁️ OCI ARM Cluster</span>
          <img src="https://upload.wikimedia.org/wikipedia/commons/3/39/Kubernetes_logo_without_workmark.svg" alt="Kubernetes" class="w-20 h-20 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <img src="https://brandlogos.net/wp-content/uploads/2021/10/oracle-logo-symbol-vector-512x512.png" alt="Oracle" class="w-14 h-14 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <img src="https://kamaji.clastix.io/images/logo.png" alt="Kamaji" class="w-16 h-16 mb-4 transform group-hover/box:scale-110 transition-transform duration-300 relative z-10" />
          <span class="text-blue-800 font-medium text-lg relative z-10">Kamaji Control Plane</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Kamaji Benefits Paragraph - Outside the Tailscale container -->
  <div class="flex justify-center mt-8">
    <div class="text-base leading-relaxed text-center bg-gradient-to-r from-blue-100 to-indigo-200 dark:from-blue-800/40 dark:to-indigo-800/40 border-2 border-blue-400 dark:border-blue-500 rounded-xl p-6 text-blue-900 dark:text-blue-100 shadow-lg max-w-5xl transform hover:scale-[1.02] hover:shadow-xl transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <span class="relative z-10">
        Hosting the Kubernetes control plane in OCI using <strong>Kamaji</strong> provides exceptional benefits: <strong>zero infrastructure costs</strong> through Oracle's free tier, <strong>high availability</strong> with enterprise-grade cloud reliability, and <strong>reduced homelab complexity</strong> by offloading critical control plane components while maintaining full cluster functionality through secure Tailscale connectivity.
      </span>
    </div>
  </div>
  
  <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
    <div class="bg-gradient-to-br from-blue-50 to-blue-100 dark:from-blue-900/30 dark:to-blue-800/30 rounded-2xl p-8 shadow-xl border border-blue-200/50 dark:border-blue-600/50 backdrop-blur-sm transform hover:scale-[1.01] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-blue-500/10 rounded-full blur-2xl group-hover:bg-blue-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-6 relative z-10">
        <div class="bg-gradient-to-br from-blue-500 to-indigo-600 text-white p-3 rounded-lg shadow-lg">
          <Home class="w-6 h-6" />
        </div>
        <h3 class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-700 to-indigo-700 dark:from-blue-300 dark:to-indigo-300">Home Infrastructure</h3>
      </div>
      <div class="space-y-4 relative z-10">
        {#each architectureData.homeInfra as component, i}
          <div class="bg-white/90 dark:bg-gray-800/90 rounded-xl p-5 shadow-md border border-blue-200/50 dark:border-blue-600/50 transform hover:scale-[1.02] hover:shadow-lg transition-all duration-300" style="transition-delay: {i * 50}ms">
            <div class="flex items-center gap-3 mb-3">
              {#if component.icon}
                <div class="bg-blue-100 dark:bg-blue-900/50 p-2 rounded-lg">
                  <svelte:component this={component.icon} class="w-5 h-5 text-blue-700 dark:text-blue-300" />
                </div>
              {/if}
              <h4 class="font-bold text-blue-900 dark:text-blue-100">{component.name}</h4>
              <span class="px-3 py-1 bg-gradient-to-r from-blue-600 to-indigo-600 text-white text-xs rounded-full shadow-sm">{component.status}</span>
            </div>
            <p class="text-sm text-gray-700 dark:text-gray-300 mb-3">{component.details}</p>
            <div class="grid grid-cols-2 gap-2 text-xs">
              {#each Object.entries(component.specs) as [key, value]}
                <div class="bg-blue-50/80 dark:bg-blue-900/30 p-2 rounded-lg border-l-2 border-blue-400 hover:border-l-4 transition-all duration-200">
                  <span class="font-medium text-blue-700 dark:text-blue-300">{key}:</span>
                  <span class="text-gray-700 dark:text-gray-300 ml-1">{value}</span>
                </div>
              {/each}
            </div>
          </div>
        {/each}
      </div>
    </div>
    <div class="bg-gradient-to-br from-green-50 to-green-100 dark:from-green-900/30 dark:to-green-800/30 rounded-2xl p-8 shadow-xl border border-green-200/50 dark:border-green-600/50 backdrop-blur-sm transform hover:scale-[1.01] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-green-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-green-500/10 rounded-full blur-2xl group-hover:bg-green-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-6 relative z-10">
        <div class="bg-gradient-to-br from-green-500 to-teal-600 text-white p-3 rounded-lg shadow-lg">
          <Cloud class="w-6 h-6" />
        </div>
        <h3 class="text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-green-700 to-teal-700 dark:from-green-300 dark:to-teal-300">Oracle Cloud Services</h3>
      </div>
      <div class="space-y-4 relative z-10">
        {#each architectureData.cloudServices as component, i}
          <div class="bg-white/90 dark:bg-gray-800/90 rounded-xl p-5 shadow-md border border-green-200/50 dark:border-green-600/50 transform hover:scale-[1.02] hover:shadow-lg transition-all duration-300" style="transition-delay: {i * 50}ms">
            <div class="flex items-center gap-3 mb-3">
              {#if component.icon}
                <div class="bg-green-100 dark:bg-green-900/50 p-2 rounded-lg">
                  <svelte:component this={component.icon} class="w-5 h-5 text-green-700 dark:text-green-300" />
                </div>
              {/if}
              <h4 class="font-bold text-green-900 dark:text-green-100">{component.name}</h4>
              <span class="px-3 py-1 bg-gradient-to-r from-green-600 to-teal-600 text-white text-xs rounded-full shadow-sm">{component.status}</span>
            </div>
            <p class="text-sm text-gray-700 dark:text-gray-300 mb-3">{component.details}</p>
            <div class="grid grid-cols-1 gap-2 text-xs">
              {#each Object.entries(component.specs) as [key, value]}
                <div class="bg-green-50/80 dark:bg-green-900/30 p-2 rounded-lg border-l-2 border-green-400 hover:border-l-4 transition-all duration-200">
                  <span class="font-medium text-green-700 dark:text-green-300">{key}:</span>
                  <span class="text-gray-700 dark:text-gray-300 ml-1">{value}</span>
                </div>
              {/each}
            </div>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>