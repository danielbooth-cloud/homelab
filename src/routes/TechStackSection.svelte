<script lang="ts">
  import { ChevronRight } from '@lucide/svelte';
  type TechStack = Record<string, string[]>;
  const techStack: TechStack = {
    'External Platform': ['Oracle Cloud Infrastructure', 'Cloudflare', 'ZeroSSL', 'Github'],
    'Networking': ['Tailscale', 'Cloudflared', 'Kong Gateway', 'Nginx Ingress', 'Cert Manager'],
    'Deployment': ['GitHub Actions', 'ArgoCD', 'Terraform', 'Atmos', 'Helmfile'],
    'Platform': ['Kubernetes', 'Apache CloudStack', 'TrueNAS Scale', 'vCluster'],
    'Kubernetes Ecosystem': ['Kamaji', 'Talos Linux', 'Cluster Autoscaler', 'KEDA', 'External Secrets'],
    'Storage': ['Longhorn CSI', 'Velero', 'MinIO S3', 'Redis'],
    'Monitoring': ['Uptime Kuma', 'Grafana Alloy', 'Grafana', 'Loki', 'Mimir'],
    'Security & Identity': ['HashiCorp Vault', 'Zitadel', 'LLDAP', 'External Secrets'],
    'Local Tools': ['Lefthook', 'Detect Secrets', 'Kubesec', 'Podman']
  };
</script>

<div class="space-y-8">
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-pink)] text-[var(--color-palette-light)] p-8 rounded-3xl shadow-2xl transform hover:scale-[1.005] transition-all duration-500 relative overflow-hidden">
    <div class="absolute top-4 right-4 w-12 h-12 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-60"></div>
    <div class="absolute bottom-4 left-4 w-8 h-8 bg-[var(--color-palette-faded-pink)] rounded-full opacity-40"></div>
    <div class="relative z-10">
      <div class="mb-4">
        <h2 class="text-4xl font-black mb-2 tracking-tight">Technology Stack</h2>
        <div class="w-20 h-1 bg-[var(--color-palette-pink)] rounded-full"></div>
      </div>
      <p class="text-lg font-light leading-relaxed">Technologies and tools powering this homelab infrastructure</p>
    </div>
  </div>

  <!-- Bootstrap Environment Diagram -->
  <div class="bg-[var(--color-palette-dark)] rounded-2xl p-8 shadow-lg border-2 border-[var(--color-palette-emerald)] max-w-9xl w-full transform hover:scale-[1.005] transition-all duration-300 relative overflow-hidden group">
      
      <div class="flex items-center gap-3 mb-4 relative z-10">
        <div class="bg-[var(--color-palette-faded-emerald)] text-[var(--color-palette-light)] p-2 rounded-lg shadow-lg transform group-hover:scale-110 transition-transform duration-300">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Git_icon.svg/2048px-Git_icon.svg.png" alt="GitHub" class="w-6 h-6" />
        </div>
        <h3 class="text-xl font-bold text-[var(--color-palette-emerald)]">GitOps workflow for deploying new environments</h3>
      </div>
      <div class="space-y-4 text-[var(--color-palette-light)] relative z-10">
        <p class="text-base leading-relaxed">
          This diagram illustrates the Environment Bootstrap Process, the deployment process leverages:
        </p>
        <ul class="list-disc list-inside space-y-2 ml-4">
          <li><strong>Atmos</strong> (framework that simplifies the management and orchestration of infrastructure)</li>
          <li><strong>Helmfile</strong> (tool that simplifies deploying and managing multiple helm charts)</li>
          <li><strong>Terraform</strong> (infrastructure as code tool)</li>
          <li><strong>Github Actions</strong> (ci/cd platform that automates software development workflows)</li>
          <li><strong>ArgoCD</strong> (gitops continuous delivery tool for kubernetes)</li>
        </ul>
      </div>
    </div>

  <div class="bg-[var(--color-palette-dark)] rounded-xl p-8 shadow-lg border-2 border-[var(--color-palette-emerald)] transform hover:scale-[1.01] transition-all duration-300 relative overflow-hidden group">
    
    <div class="flex flex-col items-center space-y-8 relative z-10">
      <!-- Top: Atmos Configuration -->
      <div class="flex items-center space-x-4 bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-emerald)] px-6 py-4 rounded-lg font-mono text-sm shadow-lg transform hover:scale-105 hover:shadow-xl transition-all duration-300 cursor-pointer group/command border border-[var(--color-palette-emerald)]">
        <div class="w-3 h-3 bg-[var(--color-palette-emerald)] rounded-full animate-pulse group-hover/command:animate-bounce"></div>
        <span class="font-bold">Satmos k8s up -e ENV</span>
        <div class="text-xs transition-colors duration-300">Single-command bootstrap</div>
      </div>

      <!-- Arrow Down -->
      <div class="flex flex-col items-center">
        <div class="w-0.5 h-8 bg-[var(--color-palette-pink)]"></div>
        <div class="w-0 h-0 border-l-4 border-r-4 border-t-8 border-l-transparent border-r-transparent border-t-[var(--color-palette-pink)]"></div>
      </div>

      <!-- Middle: Terraform Infrastructure Circle -->
      <div class="relative group/center">
        <div class="w-70 h-70 rounded-full border-4 border-[var(--color-palette-emerald)] bg-[var(--color-palette-faded-slate)] flex flex-col items-center justify-center shadow-lg transform group-hover/center:scale-[1.05] group-hover/center:shadow-2xl group-hover/center:border-[var(--color-palette-pink)] transition-all duration-500 cursor-pointer">
          
          <div class="text-center space-y-2 relative z-10">
            <div class="w-12 h-12 bg-[var(--color-palette-faded-emerald)] group-hover/center:bg-[var(--color-palette-emerald)] rounded-lg flex items-center justify-center mx-auto transform group-hover/center:scale-110 transition-all duration-300]">
              <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="GitHub" class="w-8 h-8" />
            </div>
            <div class="font-bold text-[var(--color-palette-light)] group-hover/center:text-[var(--color-palette-emerald)] transition-colors duration-300">IaC Repo</div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://atmos.tools/img/atmos-logo.svg" alt="Atmos" class="w-6 h-6" />
              <span class="text-[var(--color-palette-light)] group-hover/center:text-[var(--color-palette-emerald)] transition-colors duration-300">Atmos Stacks</span>
            </div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://avatars.githubusercontent.com/u/83191469?s=280&v=4" alt="Helmfile" class="w-6 h-6" />
              <span class="text-[var(--color-palette-light)] group-hover/center:text-[var(--color-palette-emerald)] transition-colors duration-300">Helmfile Bootstrap Files</span>
            </div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://img.icons8.com/fluent/512/terraform.png" alt="Terraform" class="w-6 h-6" />
              <span class="text-[var(--color-palette-light)] group-hover/center:text-[var(--color-palette-emerald)] transition-colors duration-300">Terraform Infra</span>
            </div>
          </div>
        </div>

        <!-- Diagonal Arrows to Clusters (Fixed z-index) -->
        <div class="absolute bottom-0 -left-16 transform translate-y-8 -rotate-45 z-20">
          <div class="flex items-center">
            <div class="w-0 h-0 border-t-4 border-b-4 border-r-8 border-t-transparent border-b-transparent border-r-[var(--color-palette-pink)]"></div>
<div class="w-20 h-0.5 bg-[var(--color-palette-pink)]"></div>
          </div>
        </div>
        <div class="absolute bottom-0 -right-16 transform translate-y-8 rotate-45 z-20">
          <div class="flex items-center">
            <div class="w-20 h-0.5 bg-[var(--color-palette-emerald)]"></div>
<div class="w-0 h-0 border-t-4 border-b-4 border-l-8 border-t-transparent border-b-transparent border-l-[var(--color-palette-emerald)]"></div>
          </div>
        </div>
      </div>

      <!-- Bottom: Kubernetes Clusters -->
      <div class="flex justify-between w-full max-w-4xl space-x-8">
        <!-- Test Cluster -->
        <div class="flex-1 bg-[var(--color-palette-faded-emerald)] border-2 border-[var(--color-palette-emerald)] rounded-xl p-6 transform hover:scale-[1.02] hover:shadow-xl hover:border-[var(--color-palette-emerald)] transition-all duration-300 cursor-pointer group/test relative overflow-hidden">
          <div class="text-center space-y-4 relative z-10">
            <div class="w-12 h-12 items-center justify-center mx-auto transform group-hover/test:scale-110 group-hover/test:rotate-12 transition-all duration-300">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-12 mb-2" />
            </div>
            <div class="font-bold text-[var(--color-palette-emerald)] group-hover/test:text-[var(--color-palette-emerald)] transition-colors duration-300">test cluster</div>
            <div class="grid grid-cols-3 gap-2 mt-4">
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
            </div>
            <div class="text-sm text-[var(--color-palette-light)] font-bold">Deployed Apps</div>
            <div class="flex items-center justify-center space-x-2 transform group-hover/test:scale-105 transition-transform duration-300">
              <img src="https://icon.icepanel.io/Technology/svg/Argo-CD.svg" alt="ArgoCD" class="w-12 h-12" />
              <span class="text-sm text-[var(--color-palette-light)]">ArgoCD ENV=test</span>
            </div>
          </div>
        </div>

        <!-- Production Cluster -->
        <div class="flex-1 bg-[var(--color-palette-faded-pink)] border-2 border-[var(--color-palette-pink)] rounded-xl p-6 transform hover:scale-[1.02] hover:shadow-xl hover:border-[var(--color-palette-pink)] transition-all duration-300 cursor-pointer group/prod relative overflow-hidden">
          <div class="text-center space-y-4 relative z-10">
            <div class="w-12 h-12 items-center justify-center mx-auto transform group-hover/prod:scale-110 group-hover/prod:rotate-12 transition-all duration-300">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-12 mb-2" />
            </div>
            <div class="font-bold text-[var(--color-palette-pink)] group-hover/prod:text-[var(--color-palette-pink)] transition-colors duration-300">prod cluster</div>
            <div class="grid grid-cols-3 gap-2 mt-4">
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
            </div>
            <div class="text-sm text-[var(--color-palette-light)] font-bold">Deployed Apps</div>
            <div class="flex items-center justify-center space-x-2 transform group-hover/prod:scale-105 transition-transform duration-300">
              <img src="https://icon.icepanel.io/Technology/svg/Argo-CD.svg" alt="ArgoCD" class="w-12 h-12" />
              <span class="text-sm text-[var(--color-palette-light)]">ArgoCD ENV=prod</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom: GitOps -->
      <div class="flex flex-col items-center space-y-4 relative group/gitops">
        <div class="w-12 h-12 bg-[var(--color-palette-light)] rounded-full flex items-center justify-center relative transform group-hover/gitops:scale-[1.05] group-hover/gitops:shadow-xl transition-all duration-300 cursor-pointer">
          <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="GitHub" class="w-12 h-12 relative z-10" />
          
          <!-- Arrows from GitOps to Clusters (Fixed z-index and removed interactivity) -->
          <div class="absolute -top-8 -left-32 transform rotate-45 z-20">
            <div class="flex items-center">
              <div class="w-24 h-0.5 bg-[var(--color-palette-pink)]"></div>
              <div class="w-0 h-0 border-t-4 border-b-4 border-l-8 border-t-transparent border-b-transparent border-l-[var(--color-palette-pink)]"></div>
            </div>
          </div>
          <div class="absolute -top-8 -right-32 transform -rotate-45 z-20">
            <div class="flex items-center">
              <div class="w-0 h-0 border-t-4 border-b-4 border-r-8 border-t-transparent border-b-transparent border-r-[var(--color-palette-emerald)]"></div>
              <div class="w-24 h-0.5 bg-[var(--color-palette-emerald)]"></div>
            </div>
          </div>
        </div>
        <div class="text-center">
          <div class="font-bold text-[var(--color-palette-emerald)] group-hover/gitops:scale-105 transition-all duration-300">GitOps Repo</div>
          <div class="flex items-center justify-center space-x-2 mt-2 transform group-hover/gitops:scale-[1.02] transition-transform duration-300">
            <img src="https://avatars.githubusercontent.com/u/83191469?s=280&v=4" alt="Helmfile" class="w-6 h-6" />
            <span class="text-sm text-[var(--color-palette-emerald)] group-hover/gitops:text-[var(--color-palette-emerald)] transition-colors duration-300">Helmfile apps with environment overlays</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Explanation Section -->
  <div class="bg-[var(--color-palette-faded-slate)] rounded-xl p-8 shadow-lg border border-[var(--color-palette-emerald)] relative overflow-hidden transform hover:scale-[1.01] hover:shadow-xl transition-all duration-300 group cursor-pointer">
    <div class="relative z-10">
      <h3 class="text-2xl font-bold text-[var(--color-palette-emerald)] mb-4 flex items-center gap-3 transform group-hover:scale-[1.02] transition-transform duration-300">
        <div class="w-8 h-8 bg-[var(--color-palette-emerald)] rounded-lg flex items-center justify-center transform group-hover:rotate-6 group-hover:scale-[1.05] transition-all duration-300">
          <svg class="w-5 h-5 text-[var(--color-palette-light)]" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </div>
        Understanding the GitOps Workflow
      </h3>
      <div class="space-y-4 text-[var(--color-palette-emerald)]">
        <p class="text-lg leading-relaxed transform group-hover:translate-x-1 transition-transform duration-300">
          This diagram illustrates a <strong class="text-[var(--color-palette-emerald)]">GitOps architecture</strong> where each environment is bootstrapped using Atmos & ArgoCD. Services are pre-configured to enable streamlined operations, <strong class="text-[var(--color-palette-pink)]">allowing you to go from zero to a fully configured environment with a single command.</strong>
        </p>
        <div class="grid md:grid-cols-2 gap-6 mt-6">
          <div class="space-y-3 transform hover:scale-105 hover:translate-x-2 transition-all duration-300 p-4 rounded-lg bg-[var(--color-palette-faded-purple)] rounded-lg border-l-3 border-[var(--color-palette-emerald)] group/infra">
            <h4 class="font-semibold text-[var(--color-palette-emerald)] text-lg">🏗️ Infrastructure Flow (IaC Repo)</h4>
            <ul class="space-y-2 text-sm">
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></span>
                <span>Single command (<code class="bg-[var(--color-palette-faded-emerald)] px-1 rounded transition-colors duration-200">atmos k8s up -e ENV</code>) provisions entire Kubernetes clusters</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></span>
                <span>Terraform manages cloud infrastructure, networking, and cluster bootstrap</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-emerald)] rounded-full mt-2 flex-shrink-0"></span>
                <span>Helmfile bootstraps essential platform services (ArgoCD, monitoring, security)</span>
              </li>
            </ul>
          </div>
          <div class="space-y-3 transform hover:scale-105 hover:translate-x-2 transition-all duration-300 p-4 rounded-lg bg-[var(--color-palette-faded-purple)] border-l-3 border-[var(--color-palette-pink)] group/app">
            <h4 class="font-semibold text-[var(--color-palette-pink)] text-lg">🚀 Application Flow (GitOps Repo)</h4>
            <ul class="space-y-2 text-sm">
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></span>
                <span class="text-[var(--color-palette-pink)]">ArgoCD continuously monitors GitOps repository for application changes</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></span>
                <span class="text-[var(--color-palette-pink)]">Helmfile environment-specific overlays enable consistent deployments across test/prod</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-[var(--color-palette-pink)] rounded-full mt-2 flex-shrink-0"></span>
                <span class="text-[var(--color-palette-pink)]">Declarative configuration ensures desired state is maintained automatically</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="bg-[var(--color-palette-faded-purple)] rounded-lg p-4 mt-6 transform hover:scale-[1.02] hover:shadow-lg transition-all duration-300">
          <h4 class="font-semibold text-[var(--color-palette-emerald)] mb-3 flex items-center gap-2">
            <span class="animate-bounce">✨</span> Key Advantages
          </h4>
          <div class="grid md:grid-cols-3 gap-4 text-sm">
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg bg-[var(--color-palette-faded-slate)] hover:bg-[var(--color-palette-faded-pink)] border-l-2 border-[var(--color-palette-pink)] group/advantage">
              <span class="text-[var(--color-palette-emerald)] font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">👨‍💻</span>
              <div>
                <strong class="text-[var(--color-palette-pink)]">Self-Service Environments:</strong> New environments are created and configured with a single command
              </div>
            </div>
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg bg-[var(--color-palette-faded-slate)] hover:bg-[var(--color-palette-faded-emerald)] border-l-2 border-[var(--color-palette-emerald)] group/advantage">
              <span class="text-[var(--color-palette-pink)] font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">⚡</span>
              <div>
                <strong class="text-[var(--color-palette-pink)]">Rapid Environment Creation:</strong> New clusters deployed in minutes, not hours
              </div>
            </div>
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg bg-[var(--color-palette-faded-slate)] hover:bg-[var(--color-palette-faded-pink)] border-l-2 border-[var(--color-palette-pink)] group/advantage">
              <span class="text-[var(--color-palette-pink)] font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">🛡️</span>
              <div>
                <strong class="text-[var(--color-palette-pink)]">Consistency & Reliability:</strong> Identical environments with version-controlled configurations
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
    {#each Object.entries(techStack) as [category, technologies], i}
      <div 
        class="bg-[var(--color-palette-faded-slate)] rounded-xl p-6 shadow-lg border border-[var(--color-palette-emerald)] transform hover:scale-[1.015] hover:shadow-xl transition-all duration-300" 
        style="transition-delay: {i * 50}ms"
      >
        <h3 class="text-xl font-bold text-[var(--color-palette-light)] mb-4 border-b border-[var(--color-palette-emerald)] pb-2">
          {category}
        </h3>
        <div class="space-y-2">
          {#each technologies as tech, j}
            <div 
              class="flex items-center gap-2 text-sm transform hover:translate-x-1 transition-transform duration-200" 
              style="transition-delay: {j * 30}ms"
            >
              <ChevronRight class="w-3 h-3 text-[var(--color-palette-emerald)]" />
              <span class="text-[var(--color-palette-light)]">{tech}</span>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
</div>
