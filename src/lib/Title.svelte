<script>
  export let title;
  export let description;
</script>

<div class="relative z-10 text-center text-white px-4 max-w-4xl mx-auto py-20">
  <h1 class="text-4xl md:text-6xl font-serif mb-6">
    {title}
  </h1>
  <div class="h-px w-24 mx-auto mb-6" style="background-color: #a28468;"></div>
  <p class="text-xl md:text-2xl font-light leading-relaxed text-gray-200">
    {description}
  </p>
</div>