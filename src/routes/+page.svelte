<script lang="ts">
	import welcome from '$lib/images/us-home.jpg';
	import wedCard from '$lib/images/wed-card.jpg';
	import { Spotifly } from "spotifly";
	import type { SpotifySearchTracks } from 'spotifly/dist/types';
	const sp = new Spotifly();

	let searchTerm = '';
	let tracks: string[] = [];

	function search() {
		console.log('searching ' + searchTerm);
		if(searchTerm?.length > 3){
			sp.searchTracks(searchTerm, 5).then((res) => {
				tracks = res.data.searchV2.tracksV2.items?.map((track) => {
					const band = track.item?.data?.artists?.items?.map((artist) => artist?.profile?.name).join(', ');
					return band + ": " + track.item?.data?.name;
				});
			}).catch((err) => {
				console.error(err);
			});
		}
		
	}
</script>

<svelte:head>
	<title>Math & Mika</title>
	<meta name="description" content="Wedding site info" />
</svelte:head>

<div class="backgrounds">
	<div class="background aos-init aos-animate" data-aos="fade-in" data-aos-duration="1500" data-aos-anchor=".section--hero" style="background-image: url('src/lib/images/bg.jpeg');"></div>
</div>


<section class="hero">
	<img src={welcome} alt="Welcome" />
	<img src={wedCard} alt="Card" />
</section>

<section class="section section--code">
	<div class="container">

		<div class="code" data-aos="fade-up-right">
			<h1>Mairie, 13h30</h1>
			<p>Mairie de Douai 83 Rue de la Mairie, 59500 Douai</p>
			<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2544.9390057587643!2d3.0805721999999998!3d50.367691799999996!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c2c967c812a74f%3A0x3955107e8d5a47a2!2sMairie%20de%20Douai!5e0!3m2!1sfr!2sfr!4v1727466178463!5m2!1sfr!2sfr" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
		</div>
		<div class="code" data-aos="fade-up-left">
			<h1>Vin d'honneur, 16h</h1>
			<p>La Belle Grange 751 Bernstraete, 59270 Bailleul</p>
			<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2526.78350911202!2d2.6827663767118977!3d50.705401868973794!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47dcdf7f7fea7c77%3A0xa722ce9ba7ca02f9!2sLa%20Belle%20Grange!5e0!3m2!1sfr!2sfr!4v1727466332357!5m2!1sfr!2sfr" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
		</div>
	
		<div class="code" data-aos="fade-up-right">
			<h1>Envie de musique ?</h1>
			<form action="mailto:hktmika@gmail.com" method="post" enctype="text/plain">
				Name:<br>
				<input type="text" name="name"><br>
				Music:<br>
				<input type="text" name="track" size="50" bind:value={searchTerm}><br>
				<button on:click|preventDefault={() => search()}>Search</button>
				{#if tracks?.length > 0}
					<select name="track">
						{#each tracks as track}
							<option value={track}>{track}</option>
						{/each}
					</select>
				{/if}
				<br>
				<input type="submit" value="Send">
			</form>
		</div>
		<div class="code" data-aos="fade-up-left">
			<pre><code class="hljs xml"><span class="hljs-tag">&lt;<span class="hljs-title">div</span> <span class="hljs-attribute">data-aos</span>=<span class="hljs-value">"fade-up-left"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span></code></pre>
		</div>
		<div class="code" data-aos="fade-up-right">
			<pre><code class="hljs xml"><span class="hljs-tag">&lt;<span class="hljs-title">div</span> <span class="hljs-attribute">data-aos</span>=<span class="hljs-value">"fade-up-right"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span></code></pre>
		</div>
		<div class="code" data-aos="fade-up-left">
			<pre><code class="hljs xml"><span class="hljs-tag">&lt;<span class="hljs-title">div</span> <span class="hljs-attribute">data-aos</span>=<span class="hljs-value">"fade-up-left"</span>&gt;</span><span class="hljs-tag">&lt;/<span class="hljs-title">div</span>&gt;</span></code></pre>
		</div>
	</div>
</section>

<style lang="scss">
	
	.hero {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		height: 90dvh;
		width: 90dvw;
		margin: 5dvh 5dvw;

		img {
			height: 100%;
		}
	}
	.backgrounds, .background {
		width: 100%;
		height: 100%;
		position: fixed;
		-webkit-transform: translateZ(0);
		transform: translateZ(0);
		z-index: -1;
		background-size: cover;

		&:after {
			content: '';
			position: absolute;
			left: 0;
			right: 0;
			bottom: 0;
			top: 0;
			background: rgba(0, 0, 0, 0.5);
			opacity: 0.5;
		}
	}
	
	.code {
		width: 100%;
		clear: both;
		border-radius: 2px;
		margin: 10vh 0;
		padding: 10px;
	}

	.container {
		width: 50%;
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1, p {
		width: 100%;
		color: white;
	}


</style>
