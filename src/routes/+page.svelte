<script>
import Title from '$lib/Title.svelte';
import Features from '$lib/Features.svelte';
import MenuCTA from '$lib/MenuCTA.svelte';

let scrollY = 0;
let innerHeight = 0;
</script>

<svelte:window bind:scrollY bind:innerHeight />

<!-- Hero Section -->
<section class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gray-900">
  <div 
    class="absolute inset-0 bg-cover bg-center bg-no-repeat transition-transform duration-1000 ease-out"
    style="background-image: url(img/wide.webp); transform: translateY({scrollY * 0.5}px)"
  ></div>
  <div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/40 to-black/80"></div>
  
  <div class="relative z-10 text-center text-white px-4 max-w-4xl mx-auto">
    <div class="animate-fade-in-up">
      <h1 class="text-5xl md:text-7xl font-light mb-6 tracking-wide">
        <span class="block italic" style="color: #c5a68a;">Ristorante</span>
        <span class="block  text-white text-6xl md:text-8xl font-bold bg-gradient-to-r text-transparent bg-clip-text" style="background-image: linear-gradient(to right, #a28468, #c5a68a);">
          Universale Bistrot
        </span>
      </h1>
      <div class="h-px w-24 mx-auto mb-6" style="background-color: #a28468;"></div>
      <p class="text-xl md:text-2xl font-light mb-8 leading-relaxed text-gray-200">
        Autentici sapori liguri nel cuore di Lavagna<br>
        <span class="text-lg" style="color: #c5a68a;">Dal 1950, una tradizione di famiglia</span>
      </p>
      <a 
        href="#contatti" 
        class="inline-block text-white px-8 py-4 rounded-md text-lg font-medium transition-all duration-300 transform hover:shadow-xl"
        style="background-color: #a28468;"
        onmouseenter="this.style.backgroundColor='#8a6f56'"
        onmouseleave="this.style.backgroundColor='#a28468'"
      >
        Vieni a trovarci
      </a>
    </div>
  </div>
  
</section>

<!-- Features Section -->
<section id="servizi" class="py-20 bg-black">
  <div class="max-w-7xl mx-auto px-4">
    <Title
      title="La Nostra Eccellenza"
      description="Ogni piatto racconta una storia di passione, tradizione e qualità che si tramanda da generazioni"
    />
    
    <Features />
  </div>
</section>

<MenuCTA />

<style>
  @keyframes fade-in-up {
    from {
      opacity: 0;
      transform: translateY(-30px);
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
