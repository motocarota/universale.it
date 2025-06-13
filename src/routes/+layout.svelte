<script>
import '../app.css';
import Title from '$lib/Title.svelte';
import Orario from '$lib/Orario.svelte';
import Contatti from '$lib/Contatti.svelte';
import Mappa from '$lib/Mappa.svelte';

let scrollY = 0;
let navOpen = false;

const links = [
  { label: 'Home', url: '/' },
  { label: 'Menu', url: '/menu' },
  { label: 'Contatti', url: '#contatti' },
];

function toggleNav() {
  navOpen = !navOpen;
}

function closeNav() {
  navOpen = false;
}
</script>

<div class="min-h-screen bg-gray-900">
	<!-- Navigation -->
	<nav
	class="fixed top-0 left-0 right-0 z-50 transition-all duration-300 {scrollY > 50 ? 'bg-gray-900/95 backdrop-blur-md shadow-2xl border-b border-gray-700' : 'bg-transparent'}">

		<div class="max-w-7xl mx-auto px-4">
			<div class="flex items-center justify-end h-20">
				<!-- Logo -->
				<a href="/" class="flex items-center space-x-3 group">
					<div class="hidden sm:block">
						<div class="text-2xl font-serif font-bold text-white">
							Ristorante Universale Bistrot
						</div>
						<div class="text-sm" style="color: #a28468;">
							Dal 1950
						</div>
					</div>
					<div class="w-12 h-12 rounded-md flex items-center justify-center transform group-hover:scale-105 transition-transform duration-300" style="background-color: #a28468;">
						<span class="text-white font-serif text-xl font-bold">U</span>
					</div>
				</a>
			</div>
		</div>

		<!-- Mobile Navigation -->
		{#if navOpen}
			<div class="lg:hidden absolute top-full left-0 right-0 bg-gray-900 shadow-2xl border-b border-gray-700">
				<div class="px-4 py-6 space-y-4">
					{#each links as link}
						<a 
							href={link.url}
							on:click={closeNav}
							class="block px-4 py-3 text-gray-300 rounded-lg transition-colors duration-300 font-medium"
							onmouseenter="this.style.color='#a28468'; this.style.backgroundColor='rgb(31, 41, 55)'"
							onmouseleave="this.style.color='rgb(209, 213, 219)'; this.style.backgroundColor='transparent'"
						>
							{link.label}
						</a>
					{/each}
				</div>
			</div>
		{/if}
	</nav>

	<!-- Main Content -->
	<main>
		<slot />
	</main>


	<section class="bg-black text-gray-300">
		<div class="max-w-7xl mx-auto px-4">
			<Title
				title="Vieni a Trovarci"
				description="Ti aspettiamo nel nostro accogliente locale nel cuore di Lavagna"
			/>

			<Mappa />

			<div class="grid lg:grid-cols-2 gap-16 items-center mt-12">
				<Orario />
				<Contatti />						
			</div>
		</div>
	</section>

	<!-- Footer -->
	<footer class="bg-black text-gray-300 text-center py-12">
		<p>
			&copy; {new Date().getFullYear()} Ristorante Universale Bistrot. Tutti i diritti riservati.
		</p>
	</footer>
</div>
