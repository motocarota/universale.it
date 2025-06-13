<script>
import Title from '$lib/Title.svelte';

let scrollY = 0;
let innerHeight = 0;

let features = [
  {
    title: 'Pesce Fresco',
    desc: 'Pescato ogni giorno nelle acque del Golfo del Tigullio',
    img: 19,
  },
  {
    title: 'Tradizione Ligure',
    desc: 'Ricette autentiche tramandate di generazione in generazione',
    img: 16,
  },
  {
    title: 'Focaccia Genovese',
    desc: 'Schiacciate e focaccia al formaggio preparate secondo tradizione',
    img: 17,
  },
  {
    title: 'Terrazza Panoramica',
    desc: 'Cena sotto le stelle nel nostro incantevole giardino',
    img: 18,
  },
];
</script>

<svelte:window bind:scrollY bind:innerHeight />

<!-- Hero Section -->
<section class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gray-900">
  <div 
    class="absolute inset-0 bg-cover bg-center bg-no-repeat transition-transform duration-1000 ease-out"
    style="background-image: url(/img/1.webp); transform: translateY({scrollY * 0.5}px)"
  ></div>
  <div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/40 to-black/80"></div>
  
  <div class="relative z-10 text-center text-white px-4 max-w-4xl mx-auto">
    <div class="animate-fade-in-up">
      <h1 class="text-5xl md:text-7xl font-light mb-6 tracking-wide">
        <span class="block font-serif italic" style="color: #c5a68a;">Ristorante</span>
        <span class="block text-6xl md:text-8xl font-bold bg-gradient-to-r text-transparent bg-clip-text" style="background-image: linear-gradient(to right, #a28468, #c5a68a);">
          Universale Bistrot
        </span>
      </h1>
      <div class="h-px w-24 mx-auto mb-6" style="background-color: #a28468;"></div>
      <p class="text-xl md:text-2xl font-light mb-8 leading-relaxed text-gray-200">
        Autentici sapori liguri nel cuore di Lavagna<br>
        <span class="text-lg" style="color: #c5a68a;">Dal 1950, una tradizione di famiglia</span>
      </p>
      <a 
        href="/menu" 
        class="inline-block text-white px-8 py-4 rounded-md text-lg font-medium transition-all duration-300 transform hover:scale-105 hover:shadow-xl"
        style="background-color: #a28468;"
        onmouseenter="this.style.backgroundColor='#8a6f56'"
        onmouseleave="this.style.backgroundColor='#a28468'"
      >
        Scopri i nostri Menu
      </a>
    </div>
  </div>
  
  <!-- Scroll indicator -->
  <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" style="color: #a28468;">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
    </svg>
  </div>
</section>

<!-- Features Section -->
<section id="servizi" class="py-20 bg-black">
  <div class="max-w-7xl mx-auto px-4">
    <Title
      title="La Nostra Eccellenza"
      description="Ogni piatto racconta una storia di passione, tradizione e qualità che si tramanda da generazioni"
    />
    
    <div class="grid md:grid-cols-2 xl:grid-cols-4 gap-8">
      {#each features as feature, index}
        <div 
          class="group bg-gray-900 rounded-lg shadow-2xl transition-all duration-500 overflow-hidden transform hover:-translate-y-2 border border-gray-700"
          style="animation-delay: {index * 100}ms"
          onmouseenter="this.style.boxShadow='0 25px 50px -12px rgba(162, 132, 104, 0.2)'; this.style.borderColor='rgba(162, 132, 104, 0.5)'"
          onmouseleave="this.style.boxShadow='0 25px 50px -12px rgba(0, 0, 0, 0.25)'; this.style.borderColor='rgb(55, 65, 81)'"
        >
          <div class="relative h-64 overflow-hidden">
            <img
              src="/img/{feature.img}.webp"
              alt={feature.title}
              class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-110"
            />
            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent"></div>
          </div>
          <div class="p-6">
            <h3 class="text-xl font-serif text-white mb-3 group-hover:transition-colors duration-300" style="group-hover:color: #a28468;">
              {feature.title}
            </h3>
            <p class="text-gray-400 leading-relaxed">
              {feature.desc}
            </p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Menu CTA Section -->
<section class="relative py-32 overflow-hidden bg-gray-900">
  <div 
    class="absolute inset-0 bg-cover bg-center bg-fixed opacity-30"
    style="background-image: url(/img/29.webp);"
  ></div>
  <div class="absolute inset-0 bg-gradient-to-b from-gray-900/80 to-gray-900/90"></div>
  
  <div class="relative z-10 text-center text-white px-4">
    <div class="max-w-4xl mx-auto">
      <Title
        title="I Nostri Menu"
        description="Scopri i sapori autentici della cucina ligure, dove ogni piatto è preparato con ingredienti freschi e ricette tramandate da generazioni"
      />
      <a 
        href="/menu"
        class="inline-block bg-transparent border-2 text-lg font-medium transition-all duration-300 transform hover:scale-105 px-10 py-4 rounded-md"
        style="border-color: #a28468; color: #a28468;"
        onmouseenter="this.style.backgroundColor='#a28468'; this.style.color='#111827'"
        onmouseleave="this.style.backgroundColor='transparent'; this.style.color='#a28468'"
      >
        Consulta i Menu
      </a>
    </div>
  </div>
</section>

<style>
  @keyframes fade-in-up {
    from {
      opacity: 0;
      transform: translateY(30px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  
  .animate-fade-in-up {
    animation: fade-in-up 1s ease-out;
  }
  
  @media (prefers-reduced-motion: reduce) {
    .animate-fade-in-up,
    .animate-bounce {
      animation: none;
    }
  }
</style>
