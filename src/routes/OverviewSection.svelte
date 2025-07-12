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

<div class="space-y-12">
  <!-- Hero Section -->
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-pink)] text-[var(--color-palette-light)] p-12 rounded-3xl shadow-2xl transform hover:scale-[1.005] transition-all duration-500 relative overflow-hidden">
    <div class="absolute top-4 right-4 w-16 h-16 bg-[var(--color-palette-faded-pink)] rounded-full opacity-60"></div>
    <div class="absolute bottom-4 left-4 w-12 h-12 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-40"></div>
    <div class="relative z-10">
      <div class="flex items-center gap-4 mb-6">
        <div class="w-16 h-16 bg-[var(--color-palette-pink)] rounded-2xl flex items-center justify-center shadow-lg">
          <span class="text-3xl">🏠</span>
        </div>
        <div>
          <h1 class="text-6xl font-black mb-2 tracking-tight">Complete Home Lab</h1>
          <div class="w-24 h-1 bg-[var(--color-palette-emerald)] rounded-full"></div>
        </div>
      </div>
      <p class="text-2xl font-light leading-relaxed max-w-4xl">Enterprise-Grade Infrastructure with Kubernetes, CloudStack, AI/ML, and Zero-Trust Security</p>
    </div>
  </div>

  <!-- Stats Grid -->
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
    {#each stats as stat, i}
      <div class="group bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-faded-slate)] p-8 rounded-2xl shadow-xl hover:border-[var(--color-palette-pink)] transform hover:scale-[1.03] hover:-translate-y-2 transition-all duration-400 hover:shadow-2xl cursor-pointer" style="transition-delay: {i * 75}ms">
        <div class="flex items-center justify-between mb-4">
          <div class="w-3 h-3 bg-[var(--color-palette-emerald)] rounded-full group-hover:bg-[var(--color-palette-pink)] transition-colors duration-300"></div>
          <div class="w-8 h-1 bg-[var(--color-palette-faded-emerald)] rounded-full group-hover:bg-[var(--color-palette-faded-pink)] transition-colors duration-300"></div>
        </div>
        <div class="text-5xl font-black text-[var(--color-palette-pink)] mb-3 group-hover:text-[var(--color-palette-emerald)] transition-colors duration-300">{stat.value}</div>
        <div class="text-[var(--color-palette-light)] font-bold text-lg mb-1">{stat.label}</div>
        <div class="text-sm text-[var(--color-palette-light)] opacity-80">{stat.desc}</div>
      </div>
    {/each}
  </div>

  <!-- Feature Cards -->
  <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
    <div class="group bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-pink)] rounded-2xl p-8 shadow-2xl hover:shadow-[0_20px_50px_rgba(255,26,117,0.3)] transform hover:scale-[1.02] hover:-translate-y-1 transition-all duration-500 relative overflow-hidden">
      <div class="absolute top-0 right-0 w-32 h-32 bg-[var(--color-palette-faded-pink)] rounded-full -translate-y-16 translate-x-16 opacity-20"></div>
      <div class="relative z-10">
        <div class="flex items-center gap-4 mb-6">
          <div class="w-14 h-14 bg-[var(--color-palette-pink)] text-[var(--color-palette-light)] rounded-2xl flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform duration-300">
            <span class="text-2xl">🔗</span>
          </div>
          <div>
            <h3 class="text-2xl font-bold text-[var(--color-palette-pink)] group-hover:text-[var(--color-palette-light)] transition-colors duration-300">Tailscale Zero-Trust VPN</h3>
            <div class="w-16 h-0.5 bg-[var(--color-palette-pink)] mt-1 group-hover:w-24 transition-all duration-300"></div>
          </div>
        </div>
        <div class="space-y-4">
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">Secure WireGuard-based overlay network</span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">IP Range: <code class="bg-[var(--color-palette-faded-pink)] px-2 py-1 rounded text-sm">100.64.0.0/10</code></span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">End-to-end encryption & Zero-trust architecture</span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">Centralized authentication via Zitadel</span>
          </div>
        </div>
      </div>
    </div>
    
    <div class="group bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-emerald)] rounded-2xl p-8 shadow-2xl hover:shadow-[0_20px_50px_rgba(35,216,161,0.3)] transform hover:scale-[1.02] hover:-translate-y-1 transition-all duration-500 relative overflow-hidden">
      <div class="absolute top-0 right-0 w-32 h-32 bg-[var(--color-palette-faded-emerald)] rounded-full -translate-y-16 translate-x-16 opacity-20"></div>
      <div class="relative z-10">
        <div class="flex items-center gap-4 mb-6">
          <div class="w-14 h-14 bg-[var(--color-palette-emerald)] text-[var(--color-palette-light)] rounded-2xl flex items-center justify-center shadow-lg group-hover:scale-110 transition-transform duration-300">
            <span class="text-2xl">☁️</span>
          </div>
          <div>
            <h3 class="text-2xl font-bold text-[var(--color-palette-emerald)] group-hover:text-[var(--color-palette-light)] transition-colors duration-300">Cloudflared Tunnels</h3>
            <div class="w-16 h-0.5 bg-[var(--color-palette-emerald)] mt-1 group-hover:w-24 transition-all duration-300"></div>
          </div>
        </div>
        <div class="space-y-4">
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">Secure public access without port forwarding</span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">DDoS protection & Web Application Firewall</span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">Automatic HTTPS certificates & Global CDN</span>
          </div>
          <div class="flex items-start gap-3 text-[var(--color-palette-light)] group-hover:translate-x-1 transition-transform duration-300">
            <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></div>
            <span class="font-medium">Zero trust security architecture</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Core Technologies Section -->
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-faded-slate)] rounded-3xl p-10 shadow-2xl hover:border-[var(--color-palette-emerald)] transition-all duration-500">
    <div class="text-center mb-10">
      <div class="flex items-center justify-center gap-3 mb-4">
        <div class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full"></div>
        <h2 class="text-4xl font-black text-[var(--color-palette-light)]">Core Technologies</h2>
        <div class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full"></div>
      </div>
      <div class="w-32 h-1 bg-[var(--color-palette-emerald)] mx-auto rounded-full"></div>
    </div>
    
    <div class="grid grid-cols-2 md:grid-cols-4 gap-8">
      <a href="https://cloudstack.apache.org/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-110 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://cdn.worldvectorlogo.com/logos/apache-cloudstack.svg" alt="Apache Cloudstack" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">Apache CloudStack</span>
      </a>
      
      <a href="https://www.oracle.com/cloud/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://brandlogos.net/wp-content/uploads/2021/10/oracle-logo-symbol-vector-512x512.png" alt="OCI" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">Oracle Cloud</span>
      </a>
      
      <a href="https://kubernetes.io/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">Kubernetes</span>
      </a>
      
      <a href="https://www.truenas.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://www.osboxes.org/wp-content/uploads/2022/02/truenas-logo.png" alt="TrueNAS Scale" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">TrueNAS Scale</span>
      </a>
      
      <a href="https://www.cloudflare.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://www.cloudflare.com/favicon.ico" alt="Cloudflare" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">Cloudflare</span>
      </a>
      
      <a href="https://github.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="Github" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">GitHub</span>
      </a>
      
      <a href="https://tailscale.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="/tailscale.png" alt="Tailscale" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">Tailscale</span>
      </a>
      
      <a href="https://zerossl.com/" target="_blank" rel="noopener noreferrer" class="flex flex-col items-center bg-[var(--color-palette-faded-slate)] border border-2 border-[var(--color-palette-pink)] p-6 rounded-2xl shadow-lg transform hover:scale-105 hover:-translate-y-2 transition-all duration-400 cursor-pointer">
        <div class="w-16 h-16 mb-4 flex items-center justify-center">
          <img src="https://help.zerossl.com/hc/theming_assets/01HZKYW5S8J4F427S7AKQR697X" alt="ZeroSSL" class="h-10" />
        </div>
        <span class="font-bold text-[var(--color-palette-light)]">ZeroSSL</span>
      </a>
    </div>
  </div>
</div>