<script>
  const features = [
    {
      title: "Pesce Fresco",
      desc: "Pescato ogni giorno nelle acque del Golfo del Tigullio",
      img: 1,
    },
    {
      title: "Atmosfera unica",
      desc: "Un ambiente accogliente ed elegante per un'esperienza indimenticabile",
      img: 9,
    },
    {
      title: "Piatti autentici",
      desc: "Ricette autentiche tramandate di generazione in generazione",
      img: 5,
    },
  ];
</script>

<div class="grid md:grid-cols-2 xl:grid-cols-4 gap-8">
  {#each features as feature, index}
    <div
      class="group rounded-lg shadow-2xl transition-all duration-500 overflow-hidden transform hover:-translate-y-2"
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
        <div class="absolute inset-0"></div>
      </div>
      <div class="p-6">
        <h2
          class="text-xl text-white mb-3 group-hover:transition-colors duration-300"
        >
          {feature.title}
        </h2>
        <p class="text-gray-400 leading-relaxed">
          {feature.desc}
        </p>
      </div>
    </div>
  {/each}
</div>
