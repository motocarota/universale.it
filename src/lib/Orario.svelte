<script>
import { orario } from './orario';
</script>

<div class="p-6 border"  style="border-color: #a28468;">
  <h3 class="text-xl font-serif text-white mb-4">Orari di Apertura</h3>
  <div class="space-y-2 text-gray-300">
    {#each orario as o}
    <div class="flex justify-between">
      <span>{o.giorno}</span>
      <span class="font-medium text-gray-200">{o.orario}</span>
    </div>
    {/each}
  </div>
</div>
