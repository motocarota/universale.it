<script>
  import Contacts from "../lib/Contacts.svelte";
  import FullWidthImage from "../lib/FullWidthImage.svelte";

  let cards = [
    { title: "Pesce", desc: "Fresco appena pescato", img: 19 },
    { title: "Trattoria", desc: "I piatti della tradizione ligure", img: 16 },
    { title: "Pizzeria", desc: "Schiacciate e Focaccia al formaggio", img: 17 },
    { title: "Giardino", desc: "Con pergolato interno", img: 18 },
  ];
</script>

<div class="hero min-h-screen" style="background-image: url(/img/27.webp);">
  <div class="hero-overlay"></div>
  <div class="hero-content text-neutral-content text-center">
    <div class="max-w-md text-white">
      <h1 class="mb-5 text-6xl font-bold">Trattoria U Pescou</h1>
      <p class="mb-5 text-xl font-bold">
        Trattoria tipica genovese nel centro di Lavagna.<br />
        Venite a provare i nostri numerosi piatti, ne abbiamo davvero per tutti i
        gusti!
      </p>
      <a class="btn btn-accent btn-wide" href="/menu">Guarda i Menu</a>
    </div>
  </div>
</div>

<div
  id="servizi"
  class="min-h-screen flex flex-wrap justify-center align-center gap-3 p-11 mx-auto max-w-screen-lg"
>
  {#each cards as c}
    <div class="card bg-base-100 w-96 shadow-xl h-96">
      <figure>
        <img
          src="/img/{c.img}.webp"
          alt="car!"
          class="sepia hover:sepia-0 ease-in duration-300"
        />
      </figure>
      <div class="card-body">
        <h2 class="card-title">{c.title}</h2>
        <p>{c.desc}</p>
      </div>
    </div>
  {/each}
</div>

<FullWidthImage img="29" />

<div
  id="contatti"
  class="grid lg:grid-cols-2 gap-3 p-11 mx-auto max-w-screen-lg"
>
  <Contacts />
</div>
