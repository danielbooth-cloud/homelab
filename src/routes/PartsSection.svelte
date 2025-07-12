<script lang="ts">
  type PartItem = { name: string; price: number; specs: string };
  type PartsData = {
    [key: string]: {
      title: string;
      cost: number;
      timeline: string;
      items: PartItem[];
    }
  };

  const partsData: PartsData = {
    phase1: {
      title: 'Phase 1: Foundation',
      cost: 917, // £917 (was $1250)
      items: [
        { name: 'AMD EPYC 7302P CPU', price: 293, specs: '16c/32t, 155W TDP' }, // £293 (was $400)
        { name: 'Supermicro H12SSL-i Motherboard', price: 220, specs: '8x DDR4, 1TB max RAM' }, // £220 (was $300)
        { name: '64GB DDR4-3200 ECC RAM', price: 183, specs: '4x 16GB modules' }, // £183 (was $250)
        { name: '2x 1TB NVMe SSD', price: 88, specs: 'OS & containers' }, // £88 (was $120)
        { name: '850W 80+ Gold PSU', price: 88, specs: 'Modular, 10yr warranty' }, // £88 (was $120)
        { name: 'CPU Cooler', price: 29, specs: 'SP3 compatible' }, // £29 (was $40)
        { name: 'Fractal Design Define 7 Case', price: 59, specs: 'E-ATX, good airflow' } // £59 (was $80)
      ]
    },
    phase2: {
      title: 'Phase 2: AI/ML Capabilities',
      cost: 477, // £477 (was $650)
      items: [
        { name: 'RTX 5060 Ti 16GB', price: 367, specs: '16GB GDDR6, 40-50 tokens/sec' }, // £367 (was $500)
        { name: 'HP t640 Thin Client', price: 110, specs: 'AMD Ryzen R1505G, 8GB DDR4, 32GB eMMC, Dual 4K support' } // £110 (was $150)
      ]
    },
    phase3: {
      title: 'Phase 3: Full Expansion',
      cost: 448, // £448 (was $610)
      items: [
        { name: 'Additional 64GB ECC RAM', price: 183, specs: '128GB total capacity' }, // £183 (was $250)
        { name: 'Beelink ME Mini NAS', price: 147, specs: 'Intel N100, 12GB RAM' }, // £147 (was $200)
        { name: '2x 2TB M.2 NVME Drives', price: 117, specs: 'ZFS mirror, 4TB usable' } // £117 (was $160)
      ]
    }
  };

  let selectedPhase: string = $state('all');

  let phases = $derived.by(() => {
    if (selectedPhase === 'all') {
      return Object.values(partsData);
    }
    const phaseData = partsData[selectedPhase];
    return phaseData ? [phaseData] : [];
  });

  let totalCost = $derived.by(() => {
    if (selectedPhase === 'all') {
      return Object.values(partsData).reduce((sum, phase) => sum + (phase.cost || 0), 0);
    }
    return partsData[selectedPhase]?.cost || 0;
  });
</script>

<div class="space-y-8">
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-pink)] text-[var(--color-palette-light)] p-8 rounded-3xl shadow-2xl transform hover:scale-[1.005] transition-all duration-500 relative overflow-hidden">
    <div class="absolute top-4 right-4 w-12 h-12 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-60"></div>
    <div class="absolute bottom-4 left-4 w-8 h-8 bg-[var(--color-palette-faded-pink)] rounded-full opacity-40"></div>
    <div class="relative z-10">
      <div class="mb-4">
        <h2 class="text-4xl font-black mb-2 tracking-tight">Hardware Parts List</h2>
        <div class="w-20 h-1 bg-[var(--color-palette-pink)] rounded-full"></div>
      </div>
      <p class="text-lg font-light leading-relaxed">Components that make up this impressive homelab setup</p>
    </div>
  </div>
  <div class="flex gap-3 flex-wrap">
    {#each ['all', 'phase1', 'phase2', 'phase3'] as phase}
      <button
        onclick={() => selectedPhase = phase}
        class="px-6 py-3 rounded-xl text-sm font-bold shadow-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl {selectedPhase === phase ? 'bg-[var(--color-palette-pink)] text-[var(--color-palette-light)] border-2 border-[var(--color-palette-pink)]' : 'bg-[var(--color-palette-faded-slate)] text-[var(--color-palette-light)] border-2 border-[var(--color-palette-emerald)] hover:border-[var(--color-palette-pink)] hover:bg-[var(--color-palette-faded-pink)]'}"
      >
        {phase === 'all' ? 'Complete Build' : `Phase ${phase.slice(-1)}`}
      </button>
    {/each}
  </div>
  <div class="space-y-6">
    {#each phases as phase, i}
      <div class="bg-[var(--color-palette-faded-slate)] rounded-xl shadow-xl border border-[var(--color-palette-emerald)] p-6 transform hover:scale-[1.015] hover:shadow-2xl hover:border-[var(--color-palette-pink)] transition-all duration-300 relative overflow-hidden group" style="transition-delay: {i * 100}ms">
        <div class="absolute -top-8 -right-8 w-24 h-24 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-30 group-hover:opacity-50 transition-opacity duration-300"></div>
        <div class="flex justify-between items-center mb-6 relative z-10">
          <div>
            <h3 class="text-2xl font-bold text-[var(--color-palette-emerald)] group-hover:text-[var(--color-palette-pink)] transition-colors duration-300">{phase.title}</h3>
            <div class="w-16 h-0.5 bg-[var(--color-palette-emerald)] mt-1 group-hover:bg-[var(--color-palette-pink)] transition-colors duration-300"></div>
          </div>
          <div class="text-2xl font-bold text-[var(--color-palette-pink)] bg-[var(--color-palette-faded-pink)] px-4 py-2 rounded-lg shadow-md">£{phase.cost.toLocaleString()}</div>
        </div>
        <div class="space-y-4 relative z-10">
          {#each phase.items as item, j}
            <div class="bg-[var(--color-palette-dark)] rounded-lg p-5 border-l-4 border-[var(--color-palette-emerald)] transform hover:translate-x-2 hover:scale-[1.02] hover:border-l-[var(--color-palette-pink)] hover:shadow-lg transition-all duration-300 group/item" style="transition-delay: {j * 50}ms">
              <div class="flex justify-between items-start mb-3">
                <h4 class="font-bold text-[var(--color-palette-light)] text-lg group-hover/item:text-[var(--color-palette-emerald)] transition-colors duration-300">{item.name}</h4>
                <span class="text-xl font-bold text-[var(--color-palette-pink)] bg-[var(--color-palette-faded-pink)] px-3 py-1 rounded-lg shadow-sm">£{item.price}</span>
              </div>
              <p class="text-sm text-[var(--color-palette-light)] leading-relaxed group-hover/item:text-[var(--color-palette-emerald)] transition-colors duration-300">{item.specs}</p>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
  <div class="bg-[var(--color-palette-dark)] border-2 border-[var(--color-palette-emerald)] p-8 rounded-2xl shadow-2xl hover:border-[var(--color-palette-pink)] hover:shadow-3xl transition-all duration-500 relative overflow-hidden group">
    <div class="absolute -top-16 -right-16 w-32 h-32 bg-[var(--color-palette-faded-emerald)] rounded-full opacity-20 group-hover:opacity-40 transition-opacity duration-500"></div>
    <div class="absolute top-8 right-6 w-8 h-8 bg-[var(--color-palette-pink)] rounded-full opacity-40 animate-pulse"></div>
    <div class="absolute top-16 left-16 w-6 h-6 bg-[var(--color-palette-emerald)] rounded-full opacity-50 group-hover:bg-[var(--color-palette-pink)] transition-colors duration-300"></div>
    <div class="absolute top-20 right-12 w-10 h-10 bg-[var(--color-palette-pink)] rounded-full opacity-35 group-hover:bg-[var(--color-palette-emerald)] transition-colors duration-300"></div>
    <div class="absolute top-28 left-6 w-4 h-4 bg-[var(--color-palette-emerald)] rounded-full opacity-60 animate-pulse"></div>
    <div class="absolute bottom-8 left-8 w-12 h-12 bg-[var(--color-palette-faded-pink)] rounded-full opacity-30 group-hover:opacity-50 transition-opacity duration-300"></div>
    <div class="absolute bottom-16 right-20 w-5 h-5 bg-[var(--color-palette-emerald)] rounded-full opacity-45 group-hover:scale-110 transition-transform duration-300"></div>
    <div class="relative z-10 text-center">
      <div class="text-3xl font-black text-[var(--color-palette-emerald)] mb-2 group-hover:text-[var(--color-palette-pink)] transition-colors duration-300">
        Total Investment
      </div>
      <div class="text-4xl font-black text-[var(--color-palette-pink)] bg-[var(--color-palette-faded-pink)] px-6 py-3 rounded-xl shadow-lg inline-block transform group-hover:scale-105 transition-transform duration-300">
        £{totalCost.toLocaleString()}
      </div>
      <p class="text-[var(--color-palette-light)] mt-3 text-lg">Professional-grade homelab infrastructure</p>
    </div>
  </div>
</div>