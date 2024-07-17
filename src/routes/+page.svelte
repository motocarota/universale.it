<script>
  let cards = [{ name: "ciao" }, { name: "miao" }, { name: "bao" }];
</script>

<div
  class="hero min-h-screen"
  style="background-image: url(https://img.daisyui.com/images/stock/photo-1507358522600-9f71e620c44e.jpg);"
>
  <div class="hero-overlay bg-opacity-60"></div>
  <div class="hero-content text-neutral-content text-center">
    <div class="max-w-md">
      <h1 class="mb-5 text-5xl font-bold">Hello there</h1>
      <p class="mb-5">
        Provident cupiditate voluptatem et in. Quaerat fugiat ut assumenda
        excepturi exercitationem quasi. In deleniti eaque aut repudiandae et a
        id nisi.
      </p>
      <button class="btn btn-primary">Get Started</button>
    </div>
  </div>
</div>

<div class="min-h-screen flex flex-wrap gap-1 p-11 mx-auto max-w-screen-lg">
  {#each cards as c}
    <div class="card bg-base-100 w-96 shadow-xl h-96">
      <figure>
        <img
          src="https://img.daisyui.com/images/stock/photo-1606107557195-0e29a4b5b4aa.jpg"
          alt="car!"
        />
      </figure>
      <div class="card-body">
        <h2 class="card-title">{c.name}</h2>
        <p>How to park your car at your garage?</p>
        <div class="card-actions justify-end">
          <button class="btn btn-primary">Learn now!</button>
        </div>
      </div>
    </div>
  {/each}
</div>
