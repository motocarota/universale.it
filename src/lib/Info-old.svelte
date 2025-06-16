<script>
import Title from '$lib/Title.svelte';
import Orario from '$lib/Orario.svelte';
import Mappa from '$lib/Mappa.svelte';
import Contatti from '$lib/Contatti.svelte';
</script>

<section class="bg-black text-gray-300">
  <div class="max-w-7xl mx-auto px-4">
    <Title
      title="Vieni a Trovarci"
      description="Ti aspettiamo nel nostro accogliente locale nel cuore di Lavagna"
    />

    <Mappa />

    <div class="grid lg:grid-cols-2 gap-16 items-center mt-12">
      <Orario />
      <Contatti />						
    </div>

  </div>
</section>