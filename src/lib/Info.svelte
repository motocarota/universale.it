<script>
import Title from '$lib/Title.svelte';
import Mappa from '$lib/Mappa.svelte';
</script>

<section id="contatti" class="py-20 bg-gray-800">
  <div class="max-w-4xl mx-auto px-4 text-center">
    <Title
      title="Vieni a Trovarci"
      description="Ti aspettiamo nel nostro accogliente locale nel cuore di Lavagna"
    />
    <div class="grid md:grid-cols-2 gap-8 mb-8">
      <div class="bg-gray-900 rounded-lg p-6 shadow-2xl border border-gray-700">
        <div class="w-12 h-12 rounded-md flex items-center justify-center mx-auto mb-4" style="background-color: rgba(162, 132, 104, 0.2);">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="color: #a28468;">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-serif text-white mb-3">Orari Cucina</h3>
        <div class="text-gray-300 space-y-1">
          <div>Tutti i giorni:</div>
          <div>19:30 - 23:00</div>
          <div class="font-medium" style="color: #a28468;">Lunedì: Riposo</div>
        </div>
      </div>
      
      <a href="tel:003901851775674" class="bg-gray-900 rounded-lg p-6 shadow-2xl border border-gray-700">
        <div class="w-12 h-12 rounded-md flex items-center justify-center mx-auto mb-4" style="background-color: rgba(162, 132, 104, 0.2);">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="color: #a28468;">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-serif text-white mb-3">Prenotazioni</h3>
        <div class="text-gray-300 space-y-1">
          <div>Tel: (+39) 0185 177 5674</div>
          <div class="font-medium" style="color: #a28468;">Consigliate Soprattutto weekend</div>
        </div>
      </a>
    </div>

    <div class="mt-8 mb-8">
      <Mappa />
    </div>
    
    <div class="mt-12 p-6 rounded-lg border-l-4" style="background-color: rgba(162, 132, 104, 0.1); border-color: #a28468;">
      <p class="text-gray-300 leading-relaxed">
        <strong style="color: #a28468;">Nota:</strong> I nostri menu possono variare in base alla disponibilità del pesce fresco e dei prodotti stagionali. Vi consigliamo di chiamare per informazioni sui piatti del giorno e per eventuali allergie alimentari.
      </p>
    </div>
  </div>
</section>