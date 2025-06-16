<script>
import '../app.css';
import Navigation from '$lib/Navigation.svelte';
import Info from '$lib/Info.svelte';
</script>

<div class="min-h-screen">
	<Navigation />

	<!-- Main Content -->
	<main>
		<slot />
	</main>

	<!-- Contacts Section -->
	<Info />
	
	<!-- Footer -->
	<footer class="bg-black text-gray-300 text-center py-12">
		<p>
			&copy; {new Date().getFullYear()} Ristorante Universale Bistrot. Tutti i diritti riservati.
		</p>
	</footer>
</div>
