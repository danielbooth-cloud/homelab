<script lang="ts">
  const stats = [
    { value: '128GB', label: 'ECC RAM', desc: 'Enterprise memory' },
    { value: '16c/32t', label: 'EPYC CPU', desc: 'Server-grade processing' },
    { value: '16GB', label: 'GPU VRAM', desc: 'AI/ML acceleration' },
    { value: '4TB+', label: 'NVMe Storage', desc: 'Ultra-fast SSDs' },
    { value: '20-30', label: 'VMs', desc: 'Production workloads' },
    { value: '99.9%', label: 'Uptime', desc: 'High availability' }
  ];
</script>

<div class="space-y-8">
  <div class="bg-gradient-to-r from-blue-600 via-indigo-600 to-purple-600 text-white p-10 rounded-2xl shadow-2xl transform hover:scale-[1.01] transition-transform duration-300 relative overflow-hidden w-full">
    <div class="absolute top-0 left-0 w-full h-full bg-white/5 backdrop-blur-sm opacity-20 z-0"></div>
    <div class="absolute -top-24 -right-24 w-64 h-64 bg-white/10 rounded-full blur-3xl"></div>
    <div class="absolute -bottom-32 -left-32 w-80 h-80 bg-purple-500/10 rounded-full blur-3xl"></div>
    <div class="relative z-10 w-full">
      <h1 class="text-5xl font-extrabold mb-4 drop-shadow-md">🏠 Complete Home Lab Solution</h1>
      <p class="text-xl opacity-90 w-full">Enterprise-Grade Infrastructure with Kubernetes, CloudStack, AI/ML, and Zero-Trust Security</p>
    </div>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    {#each stats as stat, i}
      <div class="bg-white/80 dark:bg-gray-800/80 backdrop-blur-sm p-6 rounded-xl shadow-xl border border-gray-200/50 dark:border-gray-700/50 transform hover:scale-105 transition-all duration-300 hover:shadow-2xl" style="transition-delay: {i * 50}ms">
        <div class="text-4xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-indigo-600 dark:from-blue-400 dark:to-indigo-400 mb-2">{stat.value}</div>
        <div class="text-gray-900 dark:text-white font-medium">{stat.label}</div>
        <div class="text-sm text-gray-600 dark:text-gray-400">{stat.desc}</div>
      </div>
    {/each}
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
    <div class="bg-gradient-to-r from-orange-100 to-red-100 dark:from-orange-900/40 dark:to-red-900/40 border border-orange-200/50 dark:border-orange-700/50 rounded-xl p-6 shadow-xl backdrop-blur-sm transform hover:scale-[1.02] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-orange-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-orange-500/10 rounded-full blur-2xl group-hover:bg-orange-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-4">
        <div class="bg-gradient-to-br from-orange-500 to-red-500 text-white p-2 rounded-lg shadow-lg">
          <span class="text-xl">🔗</span>
        </div>
        <h3 class="text-xl font-bold text-orange-900 dark:text-orange-100">Tailscale Zero-Trust VPN Network</h3>
      </div>
      <div class="space-y-2">
        <div class="flex items-center gap-2 text-orange-800 dark:text-orange-200">
          <span class="inline-block w-2 h-2 bg-orange-500 rounded-full"></span>
          <span>Secure WireGuard-based overlay network</span>
        </div>
        <div class="flex items-center gap-2 text-orange-800 dark:text-orange-200">
          <span class="inline-block w-2 h-2 bg-orange-500 rounded-full"></span>
          <span>IP Range: 100.64.0.0/10</span>
        </div>
        <div class="flex items-center gap-2 text-orange-800 dark:text-orange-200">
          <span class="inline-block w-2 h-2 bg-orange-500 rounded-full"></span>
          <span>End-to-end encryption</span>
        </div>
        <div class="flex items-center gap-2 text-orange-800 dark:text-orange-200">
          <span class="inline-block w-2 h-2 bg-orange-500 rounded-full"></span>
          <span>Zero-trust architecture</span>
        </div>
        <div class="flex items-center gap-2 text-orange-800 dark:text-orange-200">
          <span class="inline-block w-2 h-2 bg-orange-500 rounded-full"></span>
          <span>Centralized auth via Zitadel</span>
        </div>
      </div>
    </div>
    <div class="bg-gradient-to-r from-green-100 to-blue-100 dark:from-green-900/40 dark:to-blue-900/40 border border-green-200/50 dark:border-green-700/50 rounded-xl p-6 shadow-xl backdrop-blur-sm transform hover:scale-[1.02] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-green-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-green-500/10 rounded-full blur-2xl group-hover:bg-green-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-4">
        <div class="bg-gradient-to-br from-green-500 to-blue-500 text-white p-2 rounded-lg shadow-lg">
          <span class="text-xl">☁️</span>
        </div>
        <h3 class="text-xl font-bold text-green-900 dark:text-green-100">Cloudflared Tunnels</h3>
      </div>
      <div class="space-y-2">
        <div class="flex items-center gap-2 text-green-800 dark:text-green-200">
          <span class="inline-block w-2 h-2 bg-green-500 rounded-full"></span>
          <span>Secure public access without port forwarding</span>
        </div>
        <div class="flex items-center gap-2 text-green-800 dark:text-green-200">
          <span class="inline-block w-2 h-2 bg-green-500 rounded-full"></span>
          <span>DDoS protection & WAF</span>
        </div>
        <div class="flex items-center gap-2 text-green-800 dark:text-green-200">
          <span class="inline-block w-2 h-2 bg-green-500 rounded-full"></span>
          <span>Automatic HTTPS certificates</span>
        </div>
        <div class="flex items-center gap-2 text-green-800 dark:text-green-200">
          <span class="inline-block w-2 h-2 bg-green-500 rounded-full"></span>
          <span>Global CDN edge locations</span>
        </div>
        <div class="flex items-center gap-2 text-green-800 dark:text-green-200">
          <span class="inline-block w-2 h-2 bg-green-500 rounded-full"></span>
          <span>Zero trust security</span>
        </div>
      </div>
    </div>
  </div>

  <div class="mt-12">
    <div class="bg-white/80 dark:bg-gray-800/80 rounded-2xl shadow border border-gray-200/50 dark:border-gray-700/50 p-8">
      <h2 class="text-3xl font-bold mb-6 text-center text-gray-800 dark:text-gray-100">Core Technologies</h2>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-6 justify-items-center">
        <a href="https://cloudstack.apache.org/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://cdn.worldvectorlogo.com/logos/apache-cloudstack.svg" alt="Apache Cloudstack" class="h-10 mb-2" />
          <span class="font-semibold">Apache Cloudstack</span>
        </a>
        <a href="https://www.oracle.com/cloud/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://brandlogos.net/wp-content/uploads/2021/10/oracle-logo-symbol-vector-512x512.png" alt="OCI" class="h-10 mb-2" />
          <span class="font-semibold">OCI</span>
        </a>
        <a href="https://kubernetes.io/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-10 mb-2" />
          <span class="font-semibold">Kubernetes</span>
        </a>
        <a href="https://www.truenas.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://www.osboxes.org/wp-content/uploads/2022/02/truenas-logo.png" alt="TrueNAS Scale" class="h-10 mb-2" />
          <span class="font-semibold">TrueNAS Scale</span>
        </a>
        <a href="https://www.cloudflare.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://www.cloudflare.com/favicon.ico" alt="Cloudflare" class="h-10 mb-2" />
          <span class="font-semibold">Cloudflare</span>
        </a>
        <a href="https://github.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="Github" class="h-10 mb-2" />
          <span class="font-semibold">Github</span>
        </a>
        <a href="https://tailscale.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://tailscale.com/favicon.ico" alt="Tailscale" class="h-10 mb-2" />
          <span class="font-semibold">Tailscale</span>
        </a>
        <a href="https://zerossl.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-white/80 dark:bg-gray-800/80 p-4 rounded-xl shadow border border-gray-200/50 dark:border-gray-700/50 w-full transition-transform hover:scale-105 focus:scale-105 cursor-pointer">
          <img src="https://help.zerossl.com/hc/theming_assets/01HZKYW5S8J4F427S7AKQR697X" alt="ZeroSSL" class="h-10 mb-2" />
          <span class="font-semibold">ZeroSSL</span>
        </a>
      </div>
    </div>
  </div>
</div>