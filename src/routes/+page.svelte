<script lang="ts">
	import Carousel from 'svelte-light-carousel';
	import welcome from '$lib/images/us-home.jpg';
	import dance from '$lib/sound/dance.mp3';

	let fullPic: HTMLDivElement;
	let womenImg = [];
	let menImg = [];

	[...Array(31).keys()].forEach((i) => {
		import(`$lib/images/inspi/women/${i}.jpg`).then((img) => {
			womenImg = [...womenImg, img.default];
		});
	});
	[...Array(10).keys()].forEach((i) => {
		import(`$lib/images/inspi/men/${i}.jpg`).then((img) => {
			menImg = [...menImg, img.default];
		});
	});

	let women = false;
	let men = false;
</script>

<svelte:head>
	<title>Math & Mika</title>
	<meta name="description" content="Wedding site info" />

	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
	<link
		href="https://fonts.googleapis.com/css2?family=Playwrite+VN:wght@100..400&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<header class="header">
	<div class="hero">
		<img src={welcome} alt="Welcome" />
	</div>
</header>

<nav class="sticky navbar">
	<div class="brand display__logo">
		<a href="#" class="nav__link">
			<span class="logo">Mathilde & Mickaël ~ </span><bold>27/09/25</bold></a
		>
	</div>

	<input type="checkbox" id="nav" class="hidden" />
	<label for="nav" class="nav__open"><i></i><i></i><i></i></label>
	<div class="nav">
		<ul class="nav__items">
			<li class="nav__item"><a href="#dress-code" class="nav__link">Dress code</a></li>
			<li class="nav__item"><a href="#mairie" class="nav__link">Mairie</a></li>
			<li class="nav__item"><a href="#vin" class="nav__link">Vin d'honneur</a></li>
			<li class="nav__item"><a href="#musique" class="nav__link">Musique ?</a></li>
		</ul>
	</div>
</nav>

<section class="section section--code">
	<div class="container">
		<div class="code" id="dress-code" style="background: #70162e;">
			<h1>Le dress code: années 40 !</h1>
			<p>
				On vous rassure, notre mariage n’est pas un rassemblement historique ! On ne vous demande
				pas de courir les friperies afin de trouver le graal.
			</p>
			<p>Toutefois, cela nous tient véritablement à cœur que chacun d’entre vous colle au thème.</p>
			<div class="_content" class:opened={women}>
				<h3 style="font-weight: bold; color: white">Alors Mesdames, par où commencer ?</h3>
				<p>
					On parle tout de même de 10 ans de mode alors il n’y a pas qu’une seule réponse.
					Logiquement vous trouverez chaussure à votre pied, ou plutôt, une tenue qui convient à
					votre silhouette.
				</p>
				<p>
					La guerre a nécessité l’adaptation des looks. Les tenues deviennent ainsi plus simples et
					plus fonctionnelles. Les vestes comportent des épaules carrées et les jupes sont près du
					corps, ce sont les fameuses jupes crayon ! Les tailleurs jupes sont alors très populaires.
				</p>
				<p>
					Les robes chemisiers sont un indispensable de la décennie, marquant la taille grâce à une
					ceinture. La robe Kitty Foyle est populaire : longueur au genou, base foncée, boutonnée et
					col plus clair, contrasté.
				</p>
				<p>
					Mais après la guerre, le glamour et la féminité ont fait leur grand retour ! A partir de
					1947, Dior introduit l’épaule ronde.
				</p>
				<p>
					Tailles ceintrées et jupes amples, on recherche la silhouette « sablier ». Couleurs vives
					et motifs audacieux, tout est redevenu possible.
				</p>
				<p>
					Les jupes plissées sont également dans le thème tout comme les « pantalons à la
					française », aux jambes extra larges.
				</p>
				<p style="font-weight: bold">
					Et si vous avez envie de vous la jouer star Hollywoodienne ?
				</p>
				<p>Dans ce cas, sortez vos gants de velours le satin et les paillettes !</p>
				<p>
					Plus sérieusement, les stars de la décennie sont Katharine Hepburn, Elizabeth Taylor,
					 Rita Hayworth, Veronica Lake, Lauren Bacall et Ingrid Bergman.
				</p>
				<p>Les robes sont de style grec, princesse ou encore portefeuille.</p>
				<h3 style="font-weight: bold; color: white">Comment on accessoirise ?</h3>
				<p>
					Chapeaux, turbans, écharpes, pinces à fleurs, bibi pour les cheveux . Ceintures épaisses à
					grosse boucle pour la taille.
				</p>
				<p style="font-weight: bold">Trouver chaussure à son pied.</p>
				<p>
					Cela ne fera pas plaisir à toutes mais dans les années 1940 on porte des talons ! Alors
					certes, de hauteur moyenne à basse, on cherche la praticité et la stabilité. Souvent en
					cuir ou en daim, ce sont des escarpins à bout ronds ou carrés, des mocassins et des
					chaussures à lacet. Les babies et les salomés sont également d’époque.
				</p>
				<h3 style="font-weight: bold; color: white">Et maintenant on cherche où ?</h3>
				<p>Alors mes recommandations sont les suivantes :</p>
				<ul style="color: white">
					<li>
						Top Vintage est le site de référence en tenues vintage. Vous pouvez même effectuer vos
						recherches par décennie. Cela vous permettra d’identifier des marques qui vous plaisent
						et de faire vos recherches sur Vinted si les prix sont trop élevés.
					</li>
					<li>
						Ma marque chouchoute est Voodoo Vixen, mais vous pourrez trouver chez collectif,
						Hellbunny, seamstress of bloomsburry, glamour bunny, et tant d’autres !
					</li>
					<li>
						En toute honnêteté cette année vous pourrez également trouver sur des sites tels que
						Cider.
					</li>
				</ul>
				<p style="font-weight: bold">
					Quoi qu’il arrive n’hésitez pas à m’envoyer ce que vous avez repéré !
				</p>

				<h3 style="font-weight: bold; color: white">Inspirations</h3>
				<div class="carousel-wrapper">
					<!-- <Carousel
						bind:this={carousel}
						let:loaded
						let:showPrevPage
						let:showNextPage
						style="width: 50%"
					>
						<div slot="prev" on:click={showPrevPage} class="custom-arrow custom-arrow-prev">
							<i />
						</div>
						{#each womenImg as src, imageIndex (src)}
							<div class="img-container" style="display: flex; justify-content:center;">
								{#if loaded.includes(imageIndex)}
									<img style="height: 300px; width: auto" {src} alt="inspiration" />
								{/if}
							</div>
						{/each}
						<div slot="next" on:click={showNextPage} class="custom-arrow custom-arrow-next">
							<i />
						</div>
					</Carousel> -->

	<Carousel style="height:100%" containerClass={'px-10'} slides={womenImg}  layout={{default: 1}} partialDelta={{default: 120}}>
		<div style="height:100%;" slot="slide" let:slide>
			<div style="background-image:url('{slide}');height: 100%;
    width: 100%;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;" 
	on:click={() => {
		fullPic.style.backgroundImage = 'url(' + slide + ')';
		fullPic.style.display = 'block';
	}} />
		</div>
		<div
		slot="progress"
		let:progress
		let:scrollTo
		data-progress
		on:pointerdown={scrollTo}
		class="absolute left-1/4 -bottom-5 w-1/2 overflow-hidden cursor-pointer h-2 justify-center flex items-center z-10 rounded-sm bg-slate-500"
	>
		<div
			style:transform={`scaleX(${progress}%)`}
			class="w-full h-full pointer-events-none transition-all ease-linear origin-left bg-slate-200"
		/>
	</div>
	</Carousel>

	



	
				</div>
			</div>
			<div class="_content" class:opened={men}>
				<h3 style="font-weight: bold; color: white">La mode masculine des années 40.</h3>

				<p>
					Ce qui rend la mode masculine des années 1940 unique à la décennie, c’est la coupe des
					vêtements, les motifs et les détails stylistiques qui démontraient le soutien patriotique
					d’une personne à son pays (ou son absence).
				</p>
				<p>
					Certains des détails clés de la mode masculine des années 1940 sont des pantalons taille
					haute et larges, des manteaux de costume à revers larges ,des chemises à col large, des
					cravates colorées et larges, des chaussures oxford bicolores et des chapeaux fedora à
					large bord.  Remarquez que la tendance était large ? Par rapport à la coupe skinny
					d’aujourd’hui, les années 1940 étaient axées sur le confort par le volume.
				</p>
				<p>
					La plupart des hommes ont conservé leurs vêtements des années 1930 et les ont portés
					jusqu’au début des années 40. C’était un signe de soutien à la guerre que d’être vu dans
					les costumes et les manteaux d’avant-guerre. Les chaussures ont été ressemelées et les
					chapeaux remodelés aussi longtemps que possible. Les vêtements usagés ont été transmis à
					l’appartenance familiale et transformés en looks. Les costumes étaient principalement
					vendus sans gilet. La plus grande influence des restrictions de la Seconde Guerre mondiale
					sur la mode masculine a été l’introduction de la décontraction. Les hommes étaient
					fatigués des uniformes et des costumes confinés.
				</p>

				<h3 style="font-weight: bold; color: white">LA MATIÈRE</h3>
				<p>
					Les costumes des hommes des années 1940 étaient généralement fabriqués à partir de laine
					épaisse, de laine peignée ou de tweed, mais pendant la guerre, des tissus de rayonne
					synthétique mélangés à de la laine étaient généralement utilisés à la place.
				</p>

				<h3 style="font-weight: bold; color: white">LA COULEUR</h3>
				<p>
					Les couleurs des costumes pour hommes des années 1940 étaient atténuées : noir, bleu
					marine, gris, brun foncé, beige et bleu moyen. Pendant l’été, les couleurs de tissu plus
					claires étaient le gris moyen, le brun, le bleu moyen, le bleu-vert sarcelle et le beige.
					Le blanc et l’ivoire, qui avaient été incroyablement populaires dans les années 1930, se
					sont lentement estompés, n’étant portés que dans les climats tropicaux chauds.
				</p>
				<p>
					La plupart des costumes pour hommes des années 40 n’étaient pas de couleurs unies. Le
					tweed, les chevrons, les carreaux, les rayures et les surplaids étaient des motifs de
					costume très populaires. Les larges rayures craie étaient également un motif de costume
					classique des années 40.
				</p>
				<h3 style="font-weight: bold; color: white">LA VESTE</h3>
				<p>
					La veste à simple boutonnage avait 2-3 boutons, de larges épaules rembourrées, des poches
					plaquées ou fendues et légèrement effilée à la taille. Les revers étaient larges, crantés
					ou en pointe avec des bords arrondis. La grande largeur faisait paraître un homme plus
					grand, même si la coupe était plus étroite que dans les années 30.
				</p>
				<p>
					La veste à double boutonnage était encore plus populaire dans les années 1940 en raison de
					la largeur supplémentaire qu’elle provoquait, bien que les ventes aient été limitées
					pendant les années de guerre.
				</p>
				<h3 style="font-weight: bold; color: white">LE GILET</h3>
				<p>
					Les gilets de costume pour hommes des années 1940 étaient considérés comme un gaspillage à
					la fois en temps de guerre et après, et la plupart des hommes préféraient ne pas porter de
					gilet du tout avec leurs costumes. C’était plus frais et plus confortable sans eux. Les
					gilets de costume assortis étaient coupés à col en V avec 7 à 6 boutons et des poches de
					chaque côté.
				</p>
				<h3 style="font-weight: bold; color: white">LE PANTALON</h3>
				<p>
					Les pantalons de costume, les pantalons ou les pantalons des années 1940 étaient
					généralement plats ou à plis simples. Ils étaient portés à la taille haute (au-dessus du
					nombril) avec une bande de taille de 7.5cm de large.
				</p>
				<p>
					Les jambes du pantalon étaient larges autour de la cuisse, du genou et de la cheville
					légèrement fuselée, ce qui est à l’opposé des costumes « skinny » d’aujourd’hui. Les
					pantalons larges et taille haute sont difficiles à trouver dans les magasins aujourd’hui
					(bien que cela change lentement.
				</p>
				<h3 style="font-weight: bold; color: white">LA CHEMISE</h3>
				<p>
					Les chemises habillées des hommes des années 1940 étaient généralement fabriquées en coton
					avec un grand col pointu attaché appelé col pointe de lance au début des années 1940 et un
					col classique plus court à la fin des années 1940. Les colliers modernes d’aujourd’hui
					sont beaucoup plus petits.
				</p>
				<p>
					Les chemises pour hommes des années 1940 étaient très colorées. Le blanc était une option,
					mais les hommes choisissaient des chemises bleues, beiges, jaunes, vertes ou grises à
					rayures fines ou à pois. La chemise était portée rentrée, avec une poche unique
					facultative sur la poitrine.
				</p>
				<h3 style="font-weight: bold; color: white">LES ACCESSOIRES</h3>
				<p>
					Les bretelles étaient encore portées par les hommes dans les années 1940, bien que les
					ceintures soient plus populaires. Les bretelles pour hommes des années 1940 étaient dotées
					d’épaisses bandes élastiques avec des boucles de boutonnage. Des boutons ont été cousus à
					l’intérieur de la ceinture pour attacher également des bretelles. Les bretelles étaient
					rarement visibles, portées sous un gilet de costume ou un gilet ou cachées derrière le
					costume ou le manteau.
				</p>
				<p>
					Les ceintures pour hommes des années 1940 mesuraient environ 2.5cm de large avec de
					petites boucles métalliques souvent recouvertes de cuir assorti. Le cuir de la ceinture
					était beige, marron ou noir et pouvait être uni ou grainé, tressé ou estampillé d’un motif
					western.
				</p>
				<p>
					Aucun costume d’homme des années 1940 ne serait complet sans la cravate parfaite ! Les
					cravates des années 1940 étaient fabriquées exclusivement à partir de soie, de rayonne et
					de laine. Les grandes lignes géométriques, les lignes bouclées, les monogrammes et le
					style Art déco ont été réalisés dans des couleurs patriotiques vives. Animaux, plantes,
					fleurs, oiseaux, westerns et tropicaux étaient partout.
				</p>
				<p>
					Aucun costume des années 1940 ne serait complet sans un mouchoir de poche. Ceux-ci ont été
					fabriqués à partir de rayonne ou de soie après la guerre et étaient souvent de couleurs
					vives, ou ils avaient des motifs cachemire ou d’autres motifs classiques. Les mouchoirs de
					poche des hommes des années 1940 étaient pliés en triangle et placés côté ouvert vers le
					haut, exposant deux ou trois pointes.
				</p>

				<h3 style="font-weight: bold; color: white">Inspirations</h3>
				<div class="carousel-wrapper">

					<Carousel style="height:100%" containerClass={'px-10'} slides={menImg}  layout={{default: 1}} partialDelta={{default: 120}}>
						<div style="height:100%;" slot="slide" let:slide>
							<div style="background-image:url('{slide}');height: 100%;
					width: 100%;
					background-size: contain;
					background-position: center;
					background-repeat: no-repeat;"
					on:click={() => {
						console.log('toto')
						fullPic.style.backgroundImage = 'url(' + slide + ')';
						fullPic.style.display = 'block';
					}} />
						</div>
						<div
						slot="progress"
						let:progress
						let:scrollTo
						data-progress
						on:pointerdown={scrollTo}
						class="absolute left-1/4 -bottom-5 w-1/2 overflow-hidden cursor-pointer h-2 justify-center flex items-center z-10 rounded-sm bg-slate-500"
					>
						<div
							style:transform={`scaleX(${progress}%)`}
							class="w-full h-full pointer-events-none transition-all ease-linear origin-left bg-slate-200"
						/>
					</div>
					</Carousel>
					<!-- <Carousel
						bind:this={carousel2}
						let:loaded
						let:showPrevPage2
						let:showNextPage2
						style="width: 50%"
					>
						<div slot="prev" on:click={showPrevPage2} class="custom-arrow custom-arrow-prev">
							<i />
						</div>
						{#each menImg as src, imageIndex (src)}
							<div class="img-container" style="display: flex; justify-content:center;">
								{#if loaded.includes(imageIndex)}
									<img style="height: 300px; width: auto" {src} alt="inspiration" />
								{/if}
							</div>
						{/each}
						<div slot="next" on:click={showNextPage2} class="custom-arrow custom-arrow-next">
							<i />
						</div>
					</Carousel> -->
				</div>
			</div>
			<div class="_footer">
				<button
					class="link"
					on:click={() => {
						men = false;
						women = !women;
					}}>{women ? 'Voir moins' : 'Mesdames'}</button
				>
				<button
					class="link"
					on:click={() => {
						women = false;
						men = !men;
					}}>{men ? 'Voir moins' : 'Messieurs'}</button
				>
			</div>
		</div>

		<div class="code" id="mairie" style="background: #70162e;">
			<h1>Mairie, 13h30</h1>
			<p>Mairie de Douai 83 Rue de la Mairie, 59500 Douai</p>
			<iframe
				src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2544.9390057587643!2d3.0805721999999998!3d50.367691799999996!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c2c967c812a74f%3A0x3955107e8d5a47a2!2sMairie%20de%20Douai!5e0!3m2!1sfr!2sfr!4v1727466178463!5m2!1sfr!2sfr"
				width="100%"
				height="450"
				style="border:0;"
				allowfullscreen=""
				loading="lazy"
				referrerpolicy="no-referrer-when-downgrade"
			></iframe>
		</div>

		<div class="code" id="vin" style="background: #70162e;">
			<h1>Vin d'honneur, 16h</h1>
			<p>La Belle Grange 751 Bernstraete, 59270 Bailleul</p>
			<iframe
				src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2526.78350911202!2d2.6827663767118977!3d50.705401868973794!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47dcdf7f7fea7c77%3A0xa722ce9ba7ca02f9!2sLa%20Belle%20Grange!5e0!3m2!1sfr!2sfr!4v1727466332357!5m2!1sfr!2sfr"
				width="100%"
				height="450"
				style="border:0;"
				allowfullscreen=""
				loading="lazy"
				referrerpolicy="no-referrer-when-downgrade"
			></iframe>
		</div>

		<div class="code" id="musique" style="background: #70162e;">
			<h1>Envie de musique ?</h1>
			<p>Nous ne prendrons probablement pas en compte toutes vos demandes, mais qui sait ?</p>
			<form action="mailto:vzwed2025@gmail.com" method="post" enctype="text/plain">
				<textarea
					name="tracks"
					style="width: 100%; height: 160px"
					placeholder={'artiste:titre\nartiste:titre\n...'}
				></textarea><br />

				<div style="display: flex; justify-content: flex-end;">
					<input class="button" type="submit" value="Send" />
				</div>
			</form>
		</div>
	</div>
</section>

<div bind:this={fullPic} id="fullpage" on:click={() => fullPic.style.display = 'none'}></div>

<audio id="musicplayer" autoplay style="visibility: hidden;">
	<source src={dance} />
</audio>

<style lang="scss">
	* {
		font-family: 'Roboto', serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		font-variation-settings: 'wdth' 100;
		--sc-color-rgb-light: rgb(255, 255, 255);
	}

	.carousel-wrapper {
		box-sizing: border-box;
		background-color: rgba(0, 0, 0, 0.5);
		padding: 1rem;
		border-radius: 1rem;
		display: flex;
		justify-content: center;
		width: 80%;
		height: 500px;
		margin: 0 auto 2rem auto;
	}


	:global([data-carousel-slider]) {
		height: 100% !important;
	}

	.hero {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		height: 90dvh;
		width: 100dvw;

		img {
			width: 100%;
			height: auto;
		}
	}

	.hero_title {
		font-size: 4rem;
		margin-top: -10rem;
		h1 {
			font-family: 'Playwrite VN', serif !important;
			font-optical-sizing: auto;
			font-weight: 400;
			font-style: normal;
			padding: 0;
			margin: 0;
		}
	}

	.backgrounds,
	.background {
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
		padding: 2rem;
		box-sizing: border-box;
		font-size: 1.2rem;

		h1 {
			font-family: 'Playwrite VN', serif !important;
			font-optical-sizing: auto;
			font-weight: 400;
			font-style: normal;
		}

		._content:not(.opened) {
			overflow: hidden;
			max-height: 0;
			transition: max-height 0.2s ease-out;
			text-overflow: ellipsis;
		}

		._footer {
			display: flex;
			justify-content: center;
			padding: 1rem;
			gap: 1rem;

			button.link {
				background: none;
				border: none;
				border-bottom: 1px solid white;
				color: white;
				cursor: pointer;
				font-size: 2rem;
			}
		}

		button.button,
		input.button {
			background-color: var(--primary);
			border-radius: 8px;
			border-style: none;
			box-sizing: border-box;
			color: #ffffff;
			cursor: pointer;
			display: inline-block;
			font-size: 1rem;
			font-weight: 500;
			height: 40px;
			min-width: 140px;
			line-height: 20px;
			list-style: none;
			margin: 0;
			outline: none;
			padding: 10px 16px;
			position: relative;
			text-align: center;
			text-decoration: none;
			transition: color 100ms;
			vertical-align: baseline;
			user-select: none;
			-webkit-user-select: none;
			touch-action: manipulation;
		}

		button.button:hover,
		button.button:focus,
		input.button:hover,
		input.button:focus {
			background-color: #f082ac;
		}
	}

	.container {
		width: 100%;
		overflow-y: hidden;
		box-sizing: border-box;
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1,
	p {
		width: 100%;
		color: white;
	}

	@media screen and (max-width: 768px) {
		.header {
			height: unset !important;
		}
		.hero {
			flex-direction: column;
			width: 100dvw;
			margin: 0;
			height: unset;

			img {
				width: 100%;
			}
			//second img display none
			img:nth-child(2) {
				display: none;
			}
		}

		.hero_title {
			font-size: 4rem;
			margin-top: -3rem;
		}

		.container {
			width: 100%;
		}

		.code {
			padding: 5%;
		}
	}

	:root {
		--primary: rgba(37, 37, 37, 1);
		--secondary: rgba(252, 41, 74, 1);
		--shades: rgba(238, 238, 238, 1);
	}

	* {
		scroll-behavior: smooth;
	}

	body {
		font-family: 'Source Code Pro', monospace;
		line-height: 1.6;
		margin: 0;
	}

	.header,
	#dress-code,
	#mairie,
	#vin,
	#musique {
		//height: 100vh;
	}

	.header,
	#dress-code,
	#mairie,
	#vin,
	#musique {
		position: relative;
	}

	.header h1,
	.home h1,
	.about h1,
	.portfolio h1,
	.contact h1,
	.footer h1 {
		margin: 0;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	.header h1::before,
	.home h1::before,
	.about h1::before,
	.portfolio h1::before,
	.contact h1::before,
	.footer h1::before {
		content: '#';
	}

	.header h1,
	.footer h1 {
		color: var(--shades);
	}

	.footer {
		height: 50vh;
		background-color: var(--primary);
	}

	.header {
		background-color: var(--primary);
	}

	.navbar {
		padding-top: 0.5em;
		padding-bottom: 0.5em;
		background-color: var(--primary);
		-webkit-box-shadow: 0 14px 14px -14px rgba(0, 0, 0, 0.75);
		-moz-box-shadow: 0 14px 14px -14px rgba(0, 0, 0, 0.75);
		box-shadow: 0 14px 14px -14px rgba(0, 0, 0, 0.75);
	}

	.sticky {
		position: -webkit-sticky;
		position: sticky;
		top: 0;
		z-index: 2;
	}

	.hidden {
		display: none;
	}

	.display__logo {
		font-size: 2.5rem;
		margin-bottom: 0.5rem;
		font-family: inherit;
		font-weight: 500;
		line-height: 1.2;
		color: inherit;
	}

	.nav__items {
		margin: 0;
		padding: 0;
		list-style: none;
	}

	.nav__link {
		color: var(--shades);
		text-decoration: none;
	}

	.brand {
		margin: 0;
		font-size: 1.45em;
	}

	.brand a {
		padding: 10px 15px;
		text-align: center;
		display: block;
	}

	.logo {
		display: inline-block;
		padding-top: 0.3125rem;
		padding-bottom: 0.3125rem;
		margin-right: 1rem;
		line-height: inherit;
	}

	.logo::before {
		display: inline-block;
		vertical-align: top;
		margin-right: 1rem;
		content: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" width="26" height="26" id="heart"><g fill="%23fff" transform="translate(5 -1030.698)"><circle cx="8" cy="1043.698" r="13" fill="%23ef4c45"/><path fill="%23df2209" d="M17.848 25.057a13 13 0 0 0 1.048-.471 13 13 0 0 0 1.127-.647 13 13 0 0 0 1.057-.755 13 13 0 0 0 .977-.858 13 13 0 0 0 .886-.951 13 13 0 0 0 .786-1.035 13 13 0 0 0 .68-1.108 13 13 0 0 0 .566-1.17 13 13 0 0 0 .445-1.22 13 13 0 0 0 .236-.93l-6.869-6.869-.002-.002a3.531 3.531 0 0 0-2.014-.998h-.001c-1.246-.179-2.605.26-3.608 1.264L13 9.469l-.162-.162-.002-.002c-.2-.2-.413-.379-.637-.534h-.002a4.459 4.459 0 0 0-.699-.396h-.002a4.196 4.196 0 0 0-1.5-.37c-1.016-.052-2.035.287-2.785 1.038-1.501 1.503-1.344 4.027.262 5.635l.513.513 4.662 4.666 5.2 5.2z" color="%23000" font-family="sans-serif" font-weight="400" style="line-height:normal;text-indent:0;text-align:start;text-decoration-line:none;text-decoration-style:solid;text-decoration-color:%23000;text-transform:none;block-progression:tb;isolation:auto;mix-blend-mode:normal" transform="translate(-5 1030.698)"/><path d="M4.996 2.004C3.98 1.95 2.961 2.29 2.211 3.04.71 4.544.867 7.068 2.473 8.676l.513.513 4.662 4.666a.5.5 0 0 0 .706 0l4.66-4.666.513-.513c1.606-1.608 1.762-4.132.26-5.635-1.501-1.503-4.02-1.343-5.625.264L8 3.467l-.162-.162C7.035 2.5 6.013 2.058 4.996 2.004Z" color="%23000" font-family="sans-serif" font-weight="400" overflow="visible" style="line-height:normal;text-indent:0;text-align:start;text-decoration-line:none;text-decoration-style:solid;text-decoration-color:%23000;text-transform:none;block-progression:tb;isolation:auto;mix-blend-mode:normal" transform="translate(0 1036.7)"/></g></svg>');
	}

	.nav__items {
		margin-top: 5px;
	}

	.brand .nav__link,
	.nav__items .nav__link {
		padding: 10px 15px;
		text-align: center;
		display: block;
	}

	.nav__items .nav__link {
		color: var(--shades);
		font-size: 0.99rem;
	}

	.nav__items .nav__link:hover {
		color: var(--secondary);
	}

	@media (min-width: 800px) {
		.navbar,
		.nav__items {
			display: flex;
		}

		.navbar {
			flex-direction: column;
			align-items: center;
		}

		.navbar {
			flex-direction: row;
			justify-content: space-between;
		}
	}

	

	#nav:checked + .nav__open {
		transform: rotate(45deg);
	}

	#nav:checked + .nav__open i {
		background-color: var(--shades);
		transition: transform 0.2s ease;
	}

	#nav:checked + .nav__open i:nth-child(1) {
		transform: translateY(6px) rotate(180deg);
	}

	#nav:checked + .nav__open i:nth-child(2) {
		opacity: 0;
	}

	#nav:checked ~ .nav__item a {
		display: block !important;
	}

	#nav:checked + .nav__open i:nth-child(3) {
		transform: translateY(-6px) rotate(90deg);
	}

	#nav:checked ~ .nav {
		z-index: 9990;
		opacity: 1;
		left: 0;
	}

	#nav:checked ~ .nav ul li a {
		opacity: 1;
		transform: translateY(0);
	}

	.custom-arrow {
		width: 40px;
		background-color: rgb(0, 0, 0);
		opacity: 0.3;
		position: absolute;
		top: 0px;
		bottom: 0px;
		z-index: 1;
		display: flex;
		align-items: center;
		justify-content: center;
		cursor: pointer;
		-webkit-tap-highlight-color: transparent;
		transition: opacity 150ms;
	}

	.custom-arrow-prev {
		left: 0px;
	}

	.custom-arrow-next {
		right: 0px;
	}

	.custom-arrow > i {
		position: relative;
		border-style: solid;
		border-color: rgb(255, 255, 255);
		border-image: initial;
		border-width: 0px 5px 5px 0px;
		padding: 5px;
	}

	.custom-arrow-prev > i {
		transform: rotate(135deg);
		right: -4px;
	}

	.custom-arrow-next > i {
		transform: rotate(-45deg);
		left: -4px;
	}

	[data-carousel-container] {
    position: relative;
    overflow: visible;
    min-height: 100%;
	height: 100%;
    display: flex;
    flex-direction: column;
    min-width: 100%;
}

	.btn {
    display: inline-flex;
    flex-shrink: 0;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    border-color: transparent;
    border-color: hsl(var(--b2) / var(--tw-border-opacity));
    text-align: center;
    transition-property: color,background-color,border-color,text-decoration-color,fill,stroke,opacity,box-shadow,transform,filter,-webkit-backdrop-filter;
    transition-property: color,background-color,border-color,text-decoration-color,fill,stroke,opacity,box-shadow,transform,filter,backdrop-filter;
    transition-property: color,background-color,border-color,text-decoration-color,fill,stroke,opacity,box-shadow,transform,filter,backdrop-filter,-webkit-backdrop-filter;
    transition-timing-function: cubic-bezier(.4,0,.2,1);
    transition-timing-function: cubic-bezier(0,0,.2,1);
    transition-duration: .2s;
    border-radius: var(--rounded-btn, .5rem);
    height: 3rem;
    padding-left: 1rem;
    padding-right: 1rem;
    font-size: .875rem;
    line-height: 1.25rem;
    line-height: 1em;
    min-height: 3rem;
    gap: .5rem;
    font-weight: 600;
    text-decoration-line: none;
    border-width: var(--border-btn, 1px);
    animation: button-pop var(--animation-btn, .25s) ease-out;
    text-transform: var(--btn-text-case, uppercase);
    --tw-border-opacity: 1;
    --tw-bg-opacity: 1;
    background-color: hsl(var(--b2) / var(--tw-bg-opacity));
    --tw-text-opacity: 1;
    color: hsl(var(--bc) / var(--tw-text-opacity));
    outline-color: hsl(var(--bc) / 1)
}

.opacity-50 {
    opacity: .5;
}
.\!cursor-not-allowed {
    cursor: not-allowed !important;
}
.w-fit {
    width: -moz-fit-content;
    width: fit-content;
}
.my-auto {
    margin-top: auto;
    margin-bottom: auto;
}
.top-0 {
    top: 0;
}
.left-0 {
    left: 0;
}
.bottom-0 {
    bottom: 0;
}
.absolute {
    position: absolute;
}
.w-fit {
    width: -moz-fit-content;
    width: fit-content;
}

.right-0 {
    right: 0;
}

.px-10 {
	height: 100%;
    padding-left: 2.5rem;
    padding-right: 2.5rem;
}

.aria-\[selected\=\"true\"\]\:bg-slate-100[aria-selected=true] {
    --tw-bg-opacity: 1;
    background-color: rgb(241 245 249 / var(--tw-bg-opacity));
}
.aria-\[selected\=\"true\"\]\:scale-125[aria-selected=true] {
    --tw-scale-x: 1.25;
    --tw-scale-y: 1.25;
    transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate)) skew(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x)) scaleY(var(--tw-scale-y));
}
.transition-all {
    transition-property: all;
    transition-timing-function: cubic-bezier(.4,0,.2,1);
    transition-duration: .15s;
}
.bg-slate-500 {
    --tw-bg-opacity: 1;
    background-color: rgb(100 116 139 / var(--tw-bg-opacity));
}
.rounded-full {
    border-radius: 9999px;
}
.cursor-pointer {
    cursor: pointer;
}
.w-4 {
    width: 1rem;
}
.h-4 {
    height: 1rem;
}

.w-1\/2 {
    width: 50%;
}

button, input, optgroup, select, textarea {
    font-family: inherit;
    font-feature-settings: inherit;
    font-variation-settings: inherit;
    font-size: 100%;
    font-weight: inherit;
    line-height: inherit;
    color: inherit;
    margin: 0;
    padding: 0;
}

button, [type=button], [type=reset], [type=submit] {
    -webkit-appearance: button;
    background-color: transparent;
    background-image: none;
}
button, select {
    text-transform: none;
}

*, :before, :after {
    box-sizing: border-box;
    border-width: 0;
    border-top-width: 0px;
    border-right-width: 0px;
    border-bottom-width: 0px;
    border-left-width: 0px;
    border-style: solid;
    border-top-style: solid;
    border-right-style: solid;
    border-bottom-style: solid;
    border-left-style: solid;
    border-color: #e5e7eb;
    border-top-color: rgb(229, 231, 235);
    border-right-color: rgb(229, 231, 235);
    border-bottom-color: rgb(229, 231, 235);
    border-left-color: rgb(229, 231, 235);
}

@keyframes button-pop {
    0% {
        transform: scale(var(--btn-focus-scale, .98))
    }

    40% {
        transform: scale(1.02)
    }

    to {
        transform: scale(1)
    }
}

button:active:hover,.btn:active:focus {
    animation: button-pop 0s ease-out;
    transform: scale(var(--btn-focus-scale, .97))
}

.gap-2 {
    gap: .5rem;
}
.justify-center {
    justify-content: center;
}
.items-center {
    align-items: center;
}

.flex {
    display: flex
;
}
.z-10 {
    z-index: 10;
}
.left-1\/4 {
    left: 25%;
}
.-bottom-10 {
    bottom: -2.5rem;
}
.absolute {
    position: absolute;
}

.bg-slate-500 {
    --tw-bg-opacity: 1;
    background-color: rgb(100 116 139 / var(--tw-bg-opacity));
}
.rounded-sm {
    border-radius: .125rem;
}
.overflow-hidden {
    overflow: hidden;
}
.justify-center {
    justify-content: center;
}
.items-center {
    align-items: center;
}
.cursor-pointer {
    cursor: pointer;
}
.w-1\/2 {
    width: 50%;
}
.h-2 {
    height: .5rem;
}
.flex {
    display: flex
;
}
.z-10 {
    z-index: 10;
}
.left-1\/4 {
    left: 25%;
}
.-bottom-5 {
    bottom: -2.25rem;
}

.ease-linear {
    transition-timing-function: linear;
}
.transition-all {
    transition-property: all;
    transition-timing-function: cubic-bezier(.4,0,.2,1);
    transition-duration: .15s;
}
.bg-slate-200 {
    --tw-bg-opacity: 1;
    background-color: rgb(226 232 240 / var(--tw-bg-opacity));
}
.origin-left {
    transform-origin: left;
}
.w-full {
    width: 100%;
}
.h-full {
    height: 100%;
}

#fullpage {
  display: none;
  position: fixed;
  z-index: 9999;
  top: 0;
  left: 0;
  width: 100dvw;
  height: 100dvh;
  background-size: contain;
  background-repeat: no-repeat no-repeat;
  background-position: center center;
  background-color: black;
}

@media screen and (max-width: 799px) {
		.carousel-wrapper {
			display: flex;
			justify-content: center;
			width: 100%;
		}

		.w-4 {
			width: .5rem;
		}
		.h-4 {
			height: .5rem;
		}

		.w-1\/2 {
			width: 100%;
		}


		.logo {
			display: none;
		}
		.nav {
			position: fixed;
			top: 0;
			left: 1000px;
			height: 100%;
			width: 100%;
			z-index: -1;
			background-color: var(--primary);
			opacity: 0;
			transition: all 0.2s ease;
		}

		.nav .nav__items {
			position: absolute;
			top: 50%;
			transform: translateY(-50%);
			width: 100%;
			padding-inline-start: 0;
		}

		.nav .nav__items .nav__item {
			display: block;
			float: none;
			width: 100%;
			text-align: right;
			margin-bottom: 10px;
		}

		.nav .nav__items .nav__item:nth-child(1) a {
			transition-delay: 0.2s;
		}

		.nav .nav__items .nav__item:nth-child(2) a {
			transition-delay: 0.3s;
		}

		.nav .nav__items .nav__item:nth-child(3) a {
			transition-delay: 0.4s;
		}

		.nav .nav__items .nav__item:nth-child(4) a {
			transition-delay: 0.5s;
		}

		.nav .nav__items .nav__item:not(:first-child) {
			margin-left: 0;
		}

		.nav .nav__items .nav__item .nav__link {
			padding: 10px 25px;
			opacity: 0;
			color: var(--shades);
			font-size: 24px;
			font-weight: 600;
			transform: translateY(-20px);
			transition: all 0.2s ease;
		}

		.nav .nav__items .nav__item .nav__link:hover {
			color: var(--secondary);
		}

		.nav__open {
			position: absolute;
			right: 10px;
			top: 16px;
			display: block;
			width: 48px;
			height: 48px;
			cursor: pointer;
			z-index: 9999;
			border-radius: 50%;
		}

		.nav__open i {
			display: block;
			width: 20px;
			height: 2px;
			background-color: var(--secondary);
			border-radius: 2px;
			margin-left: 14px;
		}

		.nav__open i:nth-child(1) {
			margin-top: 16px;
		}

		.nav__open i:nth-child(2) {
			margin-top: 4px;
			opacity: 1;
		}

		.nav__open i:nth-child(3) {
			margin-top: 4px;
		}
	}

</style>
