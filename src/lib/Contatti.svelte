<script>
import { contacts } from '../lib/contacts';
</script>

<div class="space-y-4">
  {#each contacts as contact}
    <a
      href={contact.url}
      target="_blank"
      class="flex items-center p-4 bg-gray-900 rounded-lg transition-all duration-300 group hover:shadow-lg border border-gray-700"
      onmouseenter="this.style.backgroundColor='rgb(55, 65, 81)'; this.style.borderColor='rgba(162, 132, 104, 0.5)'"
      onmouseleave="this.style.backgroundColor='rgb(17, 24, 39)'; this.style.borderColor='rgb(55, 65, 81)'"
    >
      <div
        class="w-12 h-12 bg-gray-800 rounded-md flex items-center justify-center mr-4 transition-colors duration-300"
        onmouseenter="this.style.backgroundColor='#a28468'"
        onmouseleave="this.style.backgroundColor='rgb(31, 41, 55)'"
      >
        <img
          src="/img/{contact.icon}.webp"
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
