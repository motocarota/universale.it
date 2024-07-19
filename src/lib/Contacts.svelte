<script>
  import { contacts } from "../lib/contacts";
</script>

<img
  src="/img/21.webp"
  alt="car!"
  class="rounded-lg"
  style="border-radius: 16px;"
/>
<div class="text-center gap-3">
  <h2 class="mb-5 text-3xl font-bold">Trattoria U Pescou</h2>
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
