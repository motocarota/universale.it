<script>
  import { contacts } from "../lib/contacts";
</script>

<div class="space-y-4">
  {#each contacts as contact}
    <a
      href={contact.url}
      target="_blank"
      class="flex items-center p-4 transition-all duration-300 group hover:shadow-lg"
      style="background-color: #a28468;"
    >
      <div
        class="w-12 h-12 rounded-md flex items-center justify-center mr-4 transition-colors duration-300"
      >
        <img
          src="img/{contact.icon}.webp"
          alt="{contact.title} icon"
          class="w-6 h-6 invert group-hover:invert-0"
        />
      </div>
      <span
        class="text-gray-300 font-medium transition-colors duration-300"
        style="group-hover:color: #a28468;"
      >
        {contact.title}
      </span>
    </a>
  {/each}
</div>
