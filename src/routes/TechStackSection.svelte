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
  <div class="bg-gradient-to-r from-purple-600 via-indigo-600 to-blue-600 text-white p-8 rounded-2xl shadow-xl relative overflow-hidden">
    <div class="absolute top-0 left-0 w-full h-full bg-white/5 backdrop-blur-sm opacity-20 z-0"></div>
    <div class="absolute -top-24 -right-24 w-64 h-64 bg-white/10 rounded-full blur-3xl"></div>
    <div class="relative z-10">
      <h2 class="text-4xl font-extrabold mb-2 drop-shadow-md">Technology Stack</h2>
      <p class="text-lg opacity-90">Cutting-edge technologies powering this homelab</p>
    </div>
  </div>

  <!-- Bootstrap Environment Diagram -->
  <div class="bg-white/90 dark:bg-gray-800/90 rounded-2xl p-8 shadow-lg border border-blue-200/50 dark:border-blue-600/50 max-w-9xl w-full transform hover:scale-[1.005] transition-all duration-300 relative overflow-hidden group">
      <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div class="absolute -top-16 -right-16 w-32 h-32 bg-blue-500/10 rounded-full blur-2xl group-hover:bg-blue-500/20 transition-colors duration-300"></div>
      <div class="flex items-center gap-3 mb-4 relative z-10">
        <div class="bg-gradient-to-br from-gray-500 to-gray-600 text-white p-2 rounded-lg shadow-lg transform group-hover:scale-110 transition-transform duration-300">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Git_icon.svg/2048px-Git_icon.svg.png" alt="GitHub" class="w-6 h-6" />
        </div>
        <h3 class="text-xl font-bold text-blue-900 dark:text-blue-100">GitOps workflow for deploying new environments</h3>
      </div>
      <div class="space-y-4 text-gray-700 dark:text-gray-300 relative z-10">
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

  <div class="bg-gradient-to-br from-white to-gray-50 dark:from-gray-800 dark:to-gray-900 rounded-xl p-8 shadow-lg border border-gray-200/50 dark:border-gray-700/50 transform hover:scale-[1.01] transition-all duration-300 relative overflow-hidden group">
    <div class="absolute inset-0 bg-gradient-to-r from-blue-500/5 via-purple-500/5 to-green-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
    <div class="absolute -top-32 -right-32 w-64 h-64 bg-blue-500/10 rounded-full blur-3xl group-hover:bg-blue-500/20 transition-colors duration-300"></div>
    <div class="flex flex-col items-center space-y-8 relative z-10">
      <!-- Top: Atmos Configuration -->
      <div class="flex items-center space-x-4 bg-gray-800 text-green-400 px-6 py-4 rounded-lg font-mono text-sm shadow-lg transform hover:scale-105 hover:shadow-xl transition-all duration-300 cursor-pointer group/command">
        <div class="w-3 h-3 bg-green-400 rounded-full animate-pulse group-hover/command:animate-bounce"></div>
        <span class="font-bold">Satmos k8s up -e ENV</span>
        <div class="text-xs opacity-75 group-hover/command:opacity-100 transition-opacity duration-300">Single-command bootstrap</div>
      </div>

      <!-- Arrow Down -->
      <div class="flex flex-col items-center">
        <div class="w-0.5 h-8 bg-gray-400 dark:bg-gray-600"></div>
        <div class="w-0 h-0 border-l-4 border-r-4 border-t-8 border-l-transparent border-r-transparent border-t-gray-400 dark:border-t-gray-600"></div>
      </div>

      <!-- Middle: Terraform Infrastructure Circle -->
      <div class="relative group/center">
        <div class="w-70 h-70 rounded-full border-4 border-gray-300 dark:border-gray-600 bg-white dark:bg-gray-800 flex flex-col items-center justify-center shadow-lg transform group-hover/center:scale-[1.05] group-hover/center:shadow-2xl group-hover/center:border-blue-400 transition-all duration-500 cursor-pointer">
          <div class="absolute inset-0 bg-gradient-to-r from-blue-500/10 via-purple-500/10 to-indigo-500/10 rounded-full opacity-0 group-hover/center:opacity-100 transition-opacity duration-300"></div>
          <div class="text-center space-y-2 relative z-10">
            <div class="w-12 h-12 bg-white-600 rounded-lg flex items-center justify-center mx-auto transform group-hover/center:scale-110 transition-transform duration-300">
              <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="GitHub" class="w-12 h-12" />
            </div>
            <div class="font-bold text-gray-700 dark:text-gray-300 group-hover/center:text-blue-600 dark:group-hover/center:text-blue-400 transition-colors duration-300">IaC Repo</div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://atmos.tools/img/atmos-logo.svg" alt="Atmos" class="w-6 h-6" />
              <span class="text-gray-600 dark:text-gray-400 group-hover/center:text-gray-700 dark:group-hover/center:text-gray-300 transition-colors duration-300">Atmos Stacks</span>
            </div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://avatars.githubusercontent.com/u/83191469?s=280&v=4" alt="Helmfile" class="w-6 h-6" />
              <span class="text-gray-600 dark:text-gray-400 group-hover/center:text-gray-700 dark:group-hover/center:text-gray-300 transition-colors duration-300">Helmfile Bootstrap Files</span>
            </div>
            <div class="flex items-center space-x-2 text-sm transform group-hover/center:scale-[1.02] transition-transform duration-300">
              <img src="https://img.icons8.com/fluent/512/terraform.png" alt="Terraform" class="w-6 h-6" />
              <span class="text-gray-600 dark:text-gray-400 group-hover/center:text-gray-700 dark:group-hover/center:text-gray-300 transition-colors duration-300">Terraform Infra</span>
            </div>
          </div>
        </div>

        <!-- Diagonal Arrows to Clusters (Fixed z-index) -->
        <div class="absolute bottom-0 -left-16 transform translate-y-8 -rotate-45 z-20">
          <div class="flex items-center">
            <div class="w-0 h-0 border-t-4 border-b-4 border-r-8 border-t-transparent border-b-transparent border-r-gray-400 dark:border-r-gray-600"></div>
            <div class="w-20 h-0.5 bg-gray-400 dark:bg-gray-600"></div>
          </div>
        </div>
        <div class="absolute bottom-0 -right-16 transform translate-y-8 rotate-45 z-20">
          <div class="flex items-center">
            <div class="w-20 h-0.5 bg-gray-400 dark:bg-gray-600"></div>
            <div class="w-0 h-0 border-t-4 border-b-4 border-l-8 border-t-transparent border-b-transparent border-l-gray-400 dark:border-l-gray-600"></div>
          </div>
        </div>
      </div>

      <!-- Bottom: Kubernetes Clusters -->
      <div class="flex justify-between w-full max-w-4xl space-x-8">
        <!-- Test Cluster -->
        <div class="flex-1 bg-blue-50 dark:bg-blue-900/20 border-2 border-blue-200 dark:border-blue-700 rounded-xl p-6 transform hover:scale-[1.02] hover:shadow-xl hover:border-blue-400 dark:hover:border-blue-500 transition-all duration-300 cursor-pointer group/test relative overflow-hidden">
          <div class="absolute inset-0 bg-blue-500/5 opacity-0 group-hover/test:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-blue-500/10 rounded-full blur-2xl group-hover/test:bg-blue-500/20 transition-colors duration-300"></div>
          <div class="text-center space-y-4 relative z-10">
            <div class="w-12 h-12 items-center justify-center mx-auto transform group-hover/test:scale-110 group-hover/test:rotate-12 transition-all duration-300">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-12 mb-2" />
            </div>
            <div class="font-bold text-blue-700 dark:text-blue-300 group-hover/test:text-blue-800 dark:group-hover/test:text-blue-200 transition-colors duration-300">test cluster</div>
            <div class="grid grid-cols-3 gap-2 mt-4">
              <div class="bg-blue-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-blue-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-blue-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
            </div>
            <div class="text-sm text-gray-600 dark:text-gray-400 font-bold group-hover/test:text-gray-700 dark:group-hover/test:text-gray-300 transition-colors duration-300">Deployed Apps</div>
            <div class="flex items-center justify-center space-x-2 transform group-hover/test:scale-105 transition-transform duration-300">
              <img src="https://icon.icepanel.io/Technology/svg/Argo-CD.svg" alt="ArgoCD" class="w-12 h-12" />
              <span class="text-sm text-gray-600 dark:text-gray-400 group-hover/test:text-gray-700 dark:group-hover/test:text-gray-300 transition-colors duration-300">ArgoCD ENV=test</span>
            </div>
          </div>
        </div>

        <!-- Production Cluster -->
        <div class="flex-1 bg-green-50 dark:bg-green-900/20 border-2 border-green-200 dark:border-green-700 rounded-xl p-6 transform hover:scale-[1.02] hover:shadow-xl hover:border-green-400 dark:hover:border-green-500 transition-all duration-300 cursor-pointer group/prod relative overflow-hidden">
          <div class="absolute inset-0 bg-green-500/5 opacity-0 group-hover/prod:opacity-100 transition-opacity duration-300"></div>
          <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-green-500/10 rounded-full blur-2xl group-hover/prod:bg-green-500/20 transition-colors duration-300"></div>
          <div class="text-center space-y-4 relative z-10">
            <div class="w-12 h-12 items-center justify-center mx-auto transform group-hover/prod:scale-110 group-hover/prod:rotate-12 transition-all duration-300">
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/723px-Kubernetes_logo_without_workmark.svg.png" alt="Kubernetes" class="h-12 mb-2" />
            </div>
            <div class="font-bold text-green-700 dark:text-green-300 group-hover/prod:text-green-800 dark:group-hover/prod:text-green-200 transition-colors duration-300">prod cluster</div>
            <div class="grid grid-cols-3 gap-2 mt-4">
              <div class="bg-green-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-green-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
              <div class="bg-green-600 text-white p-2 rounded text-xs text-center">
                <div class="text-lg">💻</div>
                <div>Apps</div>
              </div>
            </div>
            <div class="text-sm text-gray-600 dark:text-gray-400 font-bold group-hover/prod:text-gray-700 dark:group-hover/prod:text-gray-300 transition-colors duration-300">Deployed Apps</div>
            <div class="flex items-center justify-center space-x-2 transform group-hover/prod:scale-105 transition-transform duration-300">
              <img src="https://icon.icepanel.io/Technology/svg/Argo-CD.svg" alt="ArgoCD" class="w-12 h-12" />
              <span class="text-sm text-gray-600 dark:text-gray-400 group-hover/prod:text-gray-700 dark:group-hover/prod:text-gray-300 transition-colors duration-300">ArgoCD ENV=prod</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Bottom: GitOps -->
      <div class="flex flex-col items-center space-y-4 relative group/gitops">
        <div class="w-12 h-12 bg-white-800 rounded-full flex items-center justify-center relative transform group-hover/gitops:scale-[1.05] group-hover/gitops:shadow-xl transition-all duration-300 cursor-pointer">
          <img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" alt="GitHub" class="w-12 h-12 relative z-10" />
          
          <!-- Arrows from GitOps to Clusters (Fixed z-index and removed interactivity) -->
          <div class="absolute -top-8 -left-32 transform rotate-45 z-20">
            <div class="flex items-center">
              <div class="w-24 h-0.5 bg-gray-400 dark:bg-gray-600"></div>
              <div class="w-0 h-0 border-t-4 border-b-4 border-l-8 border-t-transparent border-b-transparent border-l-gray-400 dark:border-l-gray-600"></div>
            </div>
          </div>
          <div class="absolute -top-8 -right-32 transform -rotate-45 z-20">
            <div class="flex items-center">
              <div class="w-0 h-0 border-t-4 border-b-4 border-r-8 border-t-transparent border-b-transparent border-r-gray-400 dark:border-r-gray-600"></div>
              <div class="w-24 h-0.5 bg-gray-400 dark:bg-gray-600"></div>
            </div>
          </div>
        </div>
        <div class="text-center">
          <div class="font-bold text-gray-700 dark:text-gray-300 group-hover/gitops:text-purple-600 dark:group-hover/gitops:text-purple-400 transition-colors duration-300">GitOps Repo</div>
          <div class="flex items-center justify-center space-x-2 mt-2 transform group-hover/gitops:scale-[1.02] transition-transform duration-300">
            <img src="https://avatars.githubusercontent.com/u/83191469?s=280&v=4" alt="Helmfile" class="w-6 h-6" />
            <span class="text-sm text-gray-600 dark:text-gray-400 group-hover/gitops:text-gray-700 dark:group-hover/gitops:text-gray-300 transition-colors duration-300">Helmfile apps with environment overlays</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Explanation Section -->
  <div class="bg-gradient-to-br from-indigo-50 to-purple-50 dark:from-indigo-900/20 dark:to-purple-900/20 rounded-xl p-8 shadow-lg border border-indigo-200/50 dark:border-indigo-700/50 relative overflow-hidden transform hover:scale-[1.01] hover:shadow-xl transition-all duration-300 group cursor-pointer">
    <div class="absolute inset-0 bg-indigo-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
    <div class="absolute -top-16 -right-16 w-32 h-32 bg-indigo-500/10 rounded-full blur-2xl group-hover:bg-indigo-500/20 transition-colors duration-300"></div>
    <div class="relative z-10">
      <h3 class="text-2xl font-bold text-indigo-900 dark:text-indigo-100 mb-4 flex items-center gap-3 transform group-hover:scale-[1.02] transition-transform duration-300">
        <div class="w-8 h-8 bg-indigo-600 rounded-lg flex items-center justify-center transform group-hover:rotate-6 group-hover:scale-[1.05] transition-all duration-300">
          <svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </div>
        Understanding the GitOps Workflow
      </h3>
      <div class="space-y-4 text-gray-700 dark:text-gray-300">
        <p class="text-lg leading-relaxed transform group-hover:translate-x-1 transition-transform duration-300">
          This diagram illustrates a <strong class="text-indigo-700 dark:text-indigo-300">GitOps architecture</strong> where each environment is bootstrapped using Atmos & ArgoCD. Services are pre-configured to enable streamlined operations, <strong class="text-purple-700 dark:text-purple-300">allowing you to go from zero to a fully configured environment with a single command.</strong>
        </p>
        <div class="grid md:grid-cols-2 gap-6 mt-6">
          <div class="space-y-3 transform hover:scale-105 hover:translate-x-2 transition-all duration-300 p-4 rounded-lg hover:bg-indigo-50 dark:hover:bg-indigo-900/30 group/infra">
            <h4 class="font-semibold text-indigo-800 dark:text-indigo-200 text-lg group-hover/infra:text-indigo-600 dark:group-hover/infra:text-indigo-100 transition-colors duration-300">🏗️ Infrastructure Flow (IaC Repo)</h4>
            <ul class="space-y-2 text-sm">
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-indigo-500 rounded-full mt-2 flex-shrink-0 animate-pulse"></span>
                <span>Single command (<code class="bg-gray-200 dark:bg-gray-700 px-1 rounded hover:bg-indigo-100 dark:hover:bg-indigo-800 transition-colors duration-200">atmos k8s up -e ENV</code>) provisions entire Kubernetes clusters</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-indigo-500 rounded-full mt-2 flex-shrink-0"></span>
                <span>Terraform manages cloud infrastructure, networking, and cluster bootstrap</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-indigo-500 rounded-full mt-2 flex-shrink-0"></span>
                <span>Helmfile bootstraps essential platform services (ArgoCD, monitoring, security)</span>
              </li>
            </ul>
          </div>
          <div class="space-y-3 transform hover:scale-105 hover:translate-x-2 transition-all duration-300 p-4 rounded-lg hover:bg-purple-50 dark:hover:bg-purple-900/30 group/app">
            <h4 class="font-semibold text-purple-800 dark:text-purple-200 text-lg group-hover/app:text-purple-600 dark:group-hover/app:text-purple-100 transition-colors duration-300">🚀 Application Flow (GitOps Repo)</h4>
            <ul class="space-y-2 text-sm">
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-purple-500 rounded-full mt-2 flex-shrink-0 animate-pulse"></span>
                <span>ArgoCD continuously monitors GitOps repository for application changes</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-purple-500 rounded-full mt-2 flex-shrink-0"></span>
                <span>Helmfile environment-specific overlays enable consistent deployments across test/prod</span>
              </li>
              <li class="flex items-start gap-2 transform hover:translate-x-1 transition-transform duration-200">
                <span class="w-2 h-2 bg-purple-500 rounded-full mt-2 flex-shrink-0"></span>
                <span>Declarative configuration ensures desired state is maintained automatically</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="bg-white/50 dark:bg-gray-800/50 rounded-lg p-4 mt-6 transform hover:scale-[1.02] hover:bg-white/70 dark:hover:bg-gray-800/70 hover:shadow-lg transition-all duration-300">
          <h4 class="font-semibold text-gray-800 dark:text-gray-200 mb-3 flex items-center gap-2">
            <span class="animate-bounce">✨</span> Key Advantages
          </h4>
          <div class="grid md:grid-cols-3 gap-4 text-sm">
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg hover:bg-green-50 dark:hover:bg-green-900/20 group/advantage">
              <span class="text-green-600 font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">👨‍💻</span>
              <div>
                <strong class="text-green-700 dark:text-green-300">Self-Service Environments:</strong> New environments are created and configured with a single command
              </div>
            </div>
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg hover:bg-blue-50 dark:hover:bg-blue-900/20 group/advantage">
              <span class="text-blue-600 font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">⚡</span>
              <div>
                <strong class="text-blue-700 dark:text-blue-300">Rapid Environment Creation:</strong> New clusters deployed in minutes, not hours
              </div>
            </div>
            <div class="flex items-start gap-2 transform hover:scale-[1.02] hover:translate-x-0.5 transition-all duration-300 p-2 rounded-lg hover:bg-purple-50 dark:hover:bg-purple-900/20 group/advantage">
              <span class="text-purple-600 font-bold text-xl transform group-hover/advantage:scale-[1.1] transition-transform duration-300">🛡️</span>
              <div>
                <strong class="text-purple-700 dark:text-purple-300">Consistency & Reliability:</strong> Identical environments with version-controlled configurations
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
        class="bg-gradient-to-br from-white to-gray-50 dark:from-gray-800 dark:to-gray-900 rounded-xl p-6 shadow-lg border border-gray-200/50 dark:border-gray-700/50 backdrop-blur-sm transform hover:scale-[1.015] hover:shadow-xl transition-all duration-300 relative overflow-hidden group" 
        style="transition-delay: {i * 50}ms"
      >
        <div class="absolute inset-0 bg-indigo-500/5 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
        <div class="absolute -bottom-16 -right-16 w-32 h-32 bg-indigo-500/10 rounded-full blur-2xl group-hover:bg-indigo-500/20 transition-colors duration-300"></div>
        <h3 class="text-xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-indigo-700 to-purple-700 dark:from-indigo-300 dark:to-purple-300 mb-4 border-b border-gray-200 dark:border-gray-600 pb-2 relative z-10">
          {category}
        </h3>
        <div class="space-y-2 relative z-10">
          {#each technologies as tech, j}
            <div 
              class="flex items-center gap-2 text-sm transform hover:translate-x-1 transition-transform duration-200" 
              style="transition-delay: {j * 30}ms"
            >
              <ChevronRight class="w-3 h-3 text-indigo-600 dark:text-indigo-400" />
              <span class="text-gray-700 dark:text-gray-300">{tech}</span>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
</div>
