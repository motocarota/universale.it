<script>
  import FullWidthImage from "../../lib/FullWidthImage.svelte";
  const menus = [
    {
      title: "Menu dei vini",
      img: "wine",
      desc: "",
      url: "https://dnnr.it/view/pescou-vini",
    },
  ];
</script>

<FullWidthImage img="23" />

<div
  class="min-h-screen flex flex-wrap justify-center align-center gap-3 p-11 mx-auto max-w-screen-lg"
>
  {#each menus as m}
    <a class="card bg-base-100 w-96 shadow-xl h-96" href={m.url}>
      <figure>
        <img src="/img/{m.img}.webp" alt={m.title} />
      </figure>
      <div class="card-body">
        <h2 class="card-title">{m.title}</h2>
        <p>{m.desc}</p>
      </div>
    </a>
  {/each}
</div>
<div id="servizi"></div>
<div id="contatti"></div>
