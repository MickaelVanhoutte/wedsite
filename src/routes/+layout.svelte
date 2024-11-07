<script>
	import Header from './Header.svelte';
	import '../app.css';
	import Aos from 'aos';
	import { onMount } from 'svelte';
	import 'aos/dist/aos.css';

  	onMount(() => {
		Aos.init();
	});
</script>

<div class="app">
	<!-- <Header /> -->

	<main>
		<slot />
	</main>

	<!-- <footer>
		<p>visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to learn SvelteKit</p>
	</footer> -->
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
