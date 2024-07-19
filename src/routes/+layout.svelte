<script>
	import "../app.css";
	import { contacts } from "../lib/contacts";

	const links = [
		{ label: "Menu", url: "/menu" },
		{ label: "Servizi", url: "#servizi" },
		{ label: "Contatti", url: "#contatti" },
	];
</script>

<div>
	<div class="navbar bg-base-100">
		<div class="navbar-start">
			<div class="dropdown">
				<div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						fill="none"
						viewBox="0 0 24 24"
						stroke="currentColor"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							stroke-width="2"
							d="M4 6h16M4 12h8m-8 6h16"
						/>
					</svg>
				</div>
				<ul
					class="menu menu-sm dropdown-content bg-base-100 rounded-box z-[1] mt-3 w-52 p-2 shadow"
				>
					{#each links as l}
						<li>
							<a href={l.url}>{l.label}</a>
						</li>
					{/each}
				</ul>
			</div>
			<a class="btn btn-ghost text-xl" href="/">Trattoria U Pescou</a>
		</div>
		<div class="navbar-center"></div>
		<div class="navbar-end hidden lg:flex">
			<ul class="menu menu-horizontal px-1">
				{#each links as l}
					<li>
						<a href={l.url}>{l.label}</a>
					</li>
				{/each}
			</ul>
		</div>
	</div>
	<div class="min-h-80">
		<slot />
	</div>

	<footer class="footer bg-neutral text-neutral-content items-center p-4">
		<aside class="grid-flow-col items-center">
			<div>
				<p>Trattoria U Pescou</p>
				<p>Copyright © {new Date().getFullYear()} - All right reserved</p>
			</div>
		</aside>
		<nav class="grid-flow-col gap-6 md:place-self-center md:justify-self-end">
			{#each contacts as c}
				<a href={c.url} target="_blank">
					<img
						src="/img/{c.icon}.webp"
						alt="{c.title} icon"
						width="33"
						class="invert"
					/>
				</a>
			{/each}
		</nav>
	</footer>
</div>
