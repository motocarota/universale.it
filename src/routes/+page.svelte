<script>
  import { contacts } from "../lib/contacts";
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
      <h1 class="mb-5 text-6xl font-bold">Trattoria <br /> U Pescou</h1>
      <p class="mb-5 text-xl font-bold">
        Cucina tipica genovese nel centro di Lavagna.<br />
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

<div
  class="min-h-64 min-w-screen bg-slate-300 mb-8 bg-cover text-center"
  style="background-image: url(/img/29.webp);"
>
  <a href="/menu">
    <h1 class="pt-24 text-5xl font-bold text-white">Consulta i nostri menu</h1>
  </a>
</div>

<div
  id="contatti"
  class="grid lg:grid-cols-2 gap-3 p-11 mx-auto max-w-screen-lg"
>
  <img
    src="/img/21.webp"
    alt="car!"
    class="rounded-lg"
    style="border-radius: 16px;"
  />
  <div class="text-center gap-3">
    <h2 class="text-3xl font-bold">Trattoria U Pescou</h2>
    <div class="my-5">
      {#each contacts as c}
        <div class="my-4">
          <a
            href={c.url}
            target="_blank"
            class="btn btn-ghost btn-block mx-auto flex justify-between align-baseline flex-nowrap"
          >
            <img src="/img/{c.icon}.webp" alt="{c.title} icon" width="33" />
            <p>
              {c.title}
            </p>
            <p></p>
          </a>
        </div>
      {/each}
    </div>
    <div>
      <iframe
        title="map"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d4968.198095859176!2d9.342178691587371!3d44.30866864706193!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12d4980d76f46cc1%3A0xdcd170aaf9f92bad!2sU%20Pescou!5e0!3m2!1sit!2sit!4v1721374997554!5m2!1sit!2sit"
        width="300"
        height="300"
        style="border:0;"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        class="mx-auto my-4"
      />
    </div>
  </div>
</div>
