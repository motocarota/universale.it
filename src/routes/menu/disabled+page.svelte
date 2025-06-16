<script>
import Title from '$lib/Title.svelte';

const menuCategories = [
  {
    title: 'Menu dei Vini',
    subtitle: 'Selezione di vini liguri e nazionali',
    img: 'wine',
    desc: 'Scopri la nostra cantina con oltre 200 etichette selezionate',
    url: 'https://dnnr.it/view/universale-vini',
    featured: true,
  },
  {
    title: 'Antipasti di Mare',
    subtitle: 'Crudo di ricciola, acciughe del Cantabrico',
    img: '19',
    desc: 'I migliori crudi e antipasti con pesce fresco del giorno',
    url: '#',
    featured: false,
  },
  {
    title: 'Primi Piatti',
    subtitle: 'Pesto, trofie, pansotti con salsa di noci',
    img: '16',
    desc: 'Pasta fresca fatta in casa secondo la tradizione ligure',
    url: '#',
    featured: false,
  },
  {
    title: 'Secondi di Pesce',
    subtitle: 'Branzino in crosta di sale, frittura mista',
    img: '29',
    desc: 'Pesce fresco pescato quotidianamente nel Golfo del Tigullio',
    url: '#',
    featured: false,
  },
  {
    title: 'Focacce Tradizionali',
    subtitle: 'Focaccia col formaggio, farinata',
    img: '17',
    desc: 'Le specialità da forno della tradizione genovese',
    url: '#',
    featured: false,
  },
  {
    title: 'Dolci della Casa',
    subtitle: 'Panna cotta ai frutti di bosco, tiramisù',
    img: '23',
    desc: 'Dolci preparati quotidianamente dai nostri pasticceri',
    url: '#',
    featured: false,
  },
];

const specialties = [
  { name: 'Trofie al Pesto', desc: 'Con basilico del nostro orto', price: '€18' },
  { name: 'Focaccia col Formaggio', desc: 'Tradizione genovese dal 1950', price: '€12' },
  { name: 'Fritto Misto', desc: 'Pesce fresco del giorno', price: '€22' },
  { name: 'Pansotti con salsa di noci', desc: 'Pasta ripiena fatta in casa', price: '€16' },
];
</script>

<svelte:head>
  <title>Menu - Ristorante Universale Bistrot</title>
  <meta name="description" content="Scopri i nostri menu con specialità liguri, pesce fresco e tradizioni culinarie genovesi." />
</svelte:head>

<!-- Hero Section -->
<section class="relative min-h-96 flex items-center justify-center overflow-hidden bg-gray-900">
  <div 
    class="absolute inset-0 bg-cover bg-center opacity-40"
    style="background-image: url(/img/23.webp);"
  ></div>
  <div class="absolute inset-0 bg-gradient-to-b from-gray-900/70 to-gray-900/90"></div>
  
  <Title title="I Nostri Menu" description="Sapori autentici della Liguria, ricette tramandate da generazioni" />
</section>

<!-- Featured Specialties -->
<section class="py-20 bg-gray-800">
  <div class="max-w-7xl mx-auto px-4">
    <div class="text-center mb-16">
      <h2 class="text-4xl font-serif text-white mb-4">
        Le Nostre <span class="italic" style="color: #a28468;">Specialità</span>
      </h2>
      <div class="h-px w-16 mx-auto mb-6" style="background-color: #a28468;"></div>
      <p class="text-xl text-gray-300 max-w-2xl mx-auto">
        Piatti simbolo della nostra tradizione culinaria
      </p>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-16">
      {#each specialties as specialty}
        <div class="bg-gray-900 rounded-lg p-6 shadow-2xl transition-all duration-300 border border-gray-700"
             onmouseenter="this.style.boxShadow='0 25px 50px -12px rgba(162, 132, 104, 0.2)'; this.style.borderColor='rgba(162, 132, 104, 0.5)'"
             onmouseleave="this.style.boxShadow='0 25px 50px -12px rgba(0, 0, 0, 0.25)'; this.style.borderColor='rgb(55, 65, 81)'">
          <h3 class="font-serif text-lg text-white mb-2">{specialty.name}</h3>
          <p class="text-gray-400 text-sm mb-4">{specialty.desc}</p>
          <div class="flex justify-between items-center">
            <span class="text-2xl font-bold" style="color: #a28468;">{specialty.price}</span>
            <div class="w-8 h-8 rounded-md flex items-center justify-center" style="background-color: rgba(162, 132, 104, 0.2);">
              <span style="color: #a28468;">★</span>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Menu Categories -->
<section class="py-20 bg-gray-900">
  <div class="max-w-7xl mx-auto px-4">
    <div class="text-center mb-16">
      <h2 class="text-4xl font-serif text-white mb-4">
        Esplora i Nostri <span class="italic" style="color: #a28468;">Menu</span>
      </h2>
      <div class="h-px w-16 mx-auto mb-6" style="background-color: #a28468;"></div>
      <p class="text-xl text-gray-300 max-w-2xl mx-auto">
        Dalla tradizione ligure alle creazioni del nostro chef
      </p>
    </div>

    <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each menuCategories as menu, index}
        <div 
          class="group bg-gray-800 rounded-lg shadow-2xl transition-all duration-500 overflow-hidden transform hover:-translate-y-2 border border-gray-700 {menu.featured ? 'lg:col-span-2 lg:row-span-2' : ''}"
          onmouseenter="this.style.boxShadow='0 25px 50px -12px rgba(162, 132, 104, 0.2)'; this.style.borderColor='rgba(162, 132, 104, 0.5)'"
          onmouseleave="this.style.boxShadow='0 25px 50px -12px rgba(0, 0, 0, 0.25)'; this.style.borderColor='rgb(55, 65, 81)'"
        >
          <div class="relative {menu.featured ? 'h-80' : 'h-64'} overflow-hidden">
            <img
              src="/img/{menu.img}.webp"
              alt={menu.title}
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/30 to-transparent"></div>
            
            {#if menu.featured}
              <div class="absolute top-4 left-4 text-white px-3 py-1 rounded-md text-sm font-medium" style="background-color: #a28468;">
                In Evidenza
              </div>
            {/if}
            
            <div class="absolute bottom-4 left-4 right-4 text-white">
              <h3 class="text-2xl font-serif mb-2 {menu.featured ? 'text-3xl' : ''}">{menu.title}</h3>
              <p class="font-medium mb-2" style="color: #c5a68a;">{menu.subtitle}</p>
              {#if menu.featured}
                <p class="text-gray-200 text-sm">{menu.desc}</p>
              {/if}
            </div>
          </div>
          
          <div class="p-6 {menu.featured ? 'p-8' : ''}">
            {#if !menu.featured}
              <p class="text-gray-400 mb-4">{menu.desc}</p>
            {/if}
            
            <div class="flex items-center justify-between">
              <a 
                href={menu.url}
                target={menu.url.startsWith('http') ? '_blank' : '_self'}
                class="inline-flex items-center font-medium transition-colors duration-300 group-hover:underline"
                style="color: #a28468;"
                onmouseenter="this.style.color='#c5a68a'"
                onmouseleave="this.style.color='#a28468'"
              >
                {menu.url.startsWith('http') ? 'Visualizza Menu' : 'Scopri di più'}
                <svg class="w-4 h-4 ml-1 transform group-hover:translate-x-1 transition-transform duration-300" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
                </svg>
              </a>
              
              <div class="text-right">
                <div class="text-sm text-gray-500">Disponibile</div>
                <div class="text-lg font-bold text-gray-200">Tutti i giorni</div>
              </div>
            </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Info Section -->
<section class="py-20 bg-gray-800">
  <div class="max-w-4xl mx-auto px-4 text-center">
    <h2 class="text-3xl font-serif text-white mb-6">
      Informazioni <span class="italic" style="color: #a28468;">Importanti</span>
    </h2>
    <div class="grid md:grid-cols-2 gap-8">
      <div class="bg-gray-900 rounded-lg p-6 shadow-2xl border border-gray-700">
        <div class="w-12 h-12 rounded-md flex items-center justify-center mx-auto mb-4" style="background-color: rgba(162, 132, 104, 0.2);">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="color: #a28468;">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-serif text-white mb-3">Orari Cucina</h3>
        <div class="text-gray-300 space-y-1">
          <div>Pranzo: 12:00 - 14:30</div>
          <div>Cena: 19:00 - 22:30</div>
          <div class="font-medium" style="color: #a28468;">Lunedì: Riposo</div>
        </div>
      </div>
      
      <div class="bg-gray-900 rounded-lg p-6 shadow-2xl border border-gray-700">
        <div class="w-12 h-12 rounded-md flex items-center justify-center mx-auto mb-4" style="background-color: rgba(162, 132, 104, 0.2);">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="color: #a28468;">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
          </svg>
        </div>
        <h3 class="text-xl font-serif text-white mb-3">Prenotazioni</h3>
        <div class="text-gray-300 space-y-1">
          <div>Tel: (+39) 0185 392727</div>
          <div class="font-medium" style="color: #a28468;">Consigliate per cena</div>
          <div class="text-sm">Soprattutto weekend</div>
        </div>
      </div>
    </div>
    
    <div class="mt-12 p-6 rounded-lg border-l-4" style="background-color: rgba(162, 132, 104, 0.1); border-color: #a28468;">
      <p class="text-gray-300 leading-relaxed">
        <strong style="color: #a28468;">Nota:</strong> I nostri menu possono variare in base alla disponibilità del pesce fresco e dei prodotti stagionali. Vi consigliamo di chiamare per informazioni sui piatti del giorno e per eventuali allergie alimentari.
      </p>
    </div>
  </div>
</section>

<!-- Anchor elements for navigation -->
<div id="contatti"></div>
