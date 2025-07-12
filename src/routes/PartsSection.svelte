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
  <div class="bg-(--color-palette-emerald) text-(--color-palette-light) p-8 rounded-2xl shadow-xl relative overflow-hidden">
    <div class="relative z-10">
      <h2 class="text-4xl font-extrabold mb-2 drop-shadow-md">Hardware Parts List</h2>
      <p class="text-lg">Components that make up this impressive homelab setup</p>
    </div>
  </div>
  <div class="flex gap-2 flex-wrap">
    {#each ['all', 'phase1', 'phase2', 'phase3'] as phase}
      <button
        onclick={() => selectedPhase = phase}
        class="px-6 py-2.5 rounded-xl text-sm font-medium shadow-md transition-all duration-300 transform hover:scale-105 {selectedPhase === phase ? 'bg-(--color-palette-pink) text-(--color-palette-light)' : 'bg-(--color-palette-light) text-(--color-palette-emerald) border border-(--color-palette-emerald)'}"
      >
        {phase === 'all' ? 'Complete Build' : `Phase ${phase.slice(-1)}`}
      </button>
    {/each}
  </div>
  <div class="space-y-6">
    {#each phases as phase, i}
      <div class="bg-(--color-palette-light) rounded-xl shadow-xl border border-(--color-palette-emerald) p-6 transform hover:scale-[1.01] transition-all duration-300" style="transition-delay: {i * 100}ms">
        <div class="flex justify-between items-center mb-6">
          <div>
            <h3 class="text-xl font-bold text-(--color-palette-emerald)">{phase.title}</h3>
            <p class="text-(--color-palette-emerald)">{phase.timeline}</p>
          </div>
          <div class="text-xl font-bold text-(--color-palette-emerald)">£{phase.cost.toLocaleString()}</div>
        </div>
        <div class="space-y-4">
          {#each phase.items as item, j}
            <div class="bg-(--color-palette-faded-pink) rounded-lg p-4 border-l-4 border-(--color-palette-pink) transform hover:translate-x-1 transition-all duration-200" style="transition-delay: {j * 50}ms">
              <div class="flex justify-between items-start mb-2">
                <h4 class="font-bold text-(--color-palette-emerald)">{item.name}</h4>
                <span class="text-lg font-bold text-(--color-palette-pink)">£{item.price}</span>
              </div>
              <p class="text-sm text-(--color-palette-emerald)">{item.specs}</p>
            </div>
          {/each}
        </div>
      </div>
    {/each}
  </div>
  <div class="bg-(--color-palette-light) p-6 rounded-xl shadow-lg border border-(--color-palette-emerald)">
    <div class="text-2xl font-bold text-(--color-palette-emerald) text-center mt-4">
      Total Investment: £{totalCost.toLocaleString()}
    </div>
  </div>
</div>