<script lang="ts">
	import welcome from '$lib/images/us-home.jpg';
	import wedCard from '$lib/images/wed-card.jpg';
	import bg from '$lib/images/bg.jpeg';
	import dance from '$lib/sound/dance.mp3';

	let opened = false;
</script>

<svelte:head>
	<title>Math & Mika</title>
	<meta name="description" content="Wedding site info" />

	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Playwrite+VN:wght@100..400&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">

</svelte:head>


<header class="header">
	<div class="hero">
		<img src={welcome} alt="Welcome" />
		<img src={wedCard} alt="Card" />
	</div>
</header>

<nav class="sticky navbar">
	<div class="brand  display__logo">
		<a href="#top" class="nav__link"> <span class="logo">Mathilde & Mickaël wedding ~ <bold>27/09/25</bold></span></a>
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

		<div class="code" id="dress-code" style="background: rgb(197 103 103);">
			<h1>Le dress code: années 40 !</h1>
			<div class="_content" class:opened={opened}>
			<p>
				On vous rassure, notre mariage n’est pas un rassemblement historique ! On ne vous demande pas de courir les friperies afin de trouver le graal. 
			</p>
			<p>
				Toutefois, cela nous tient véritablement à cœur que chacun d’entre vous colle au thème. 
			</p>
			<h3 style="font-weight: bold; color: white">
				Alors Mesdames, par où commencer ?
			</h3>
			<p>
				On parle tout de même de 10 ans de mode alors il n’y a pas qu’une seule réponse. Logiquement vous trouverez chaussure à votre pied, ou plutôt, une tenue qui convient à votre silhouette. 
			</p>
			<p>
				La guerre a nécessité l’adaptation des looks. Les tenues deviennent ainsi plus simples et plus fonctionnelles. Les vestes comportent des épaules carrées et les jupes sont près du corps, ce sont les fameuses jupes crayon ! Les tailleurs jupes sont alors très populaires.
			</p>
			<p>
				Les robes chemisiers sont un indispensable de la décennie, marquant la taille grâce à une ceinture. La robe Kitty Foyle est populaire : longueur au genou, base foncée, boutonnée et col plus clair, contrasté.
			</p>
			<p>
				Mais après la guerre, le glamour et la féminité ont fait leur grand retour ! A partir de 1947, Dior introduit l’épaule ronde.
			</p>
			<p>
				Tailles ceintrées et jupes amples, on recherche la silhouette « sablier ». Couleurs vives et motifs audacieux, tout est redevenu possible.
			</p>
			<p>
				Les jupes plissées sont également dans le thème tout comme les « pantalons à la française », aux jambes extra larges. 
			</p>
			<p style="font-weight: bold">
				Et si vous avez envie de vous la jouer star Hollywoodienne ? 
			</p>
			<p>
				Dans ce cas, sortez vos gants de velours le satin et les paillettes ! 
			</p>
			<p>
				Plus sérieusement, les stars de la décennie sont Katharine Hepburn, Elizabeth Taylor,  Rita Hayworth, Veronica Lake, Lauren Bacall et Ingrid Bergman. 
			</p>
			<p>
				Les robes sont de style grec, princesse ou encore portefeuille. 
			</p>
			<h3 style="font-weight: bold; color: white">
				Comment on accessoirise ? 
			</h3>
			<p>
				Chapeaux, turbans, écharpes, pinces à fleurs, bibi pour les cheveux . Ceintures épaisses à grosse boucle pour la taille. 
			</p>
			<p style="font-weight: bold">
				Trouver chaussure à son pied. 
			</p>
			<p>
				Cela ne fera pas plaisir à toutes mais dans les années 1940 on porte des talons ! Alors certes, de hauteur moyenne à basse, on cherche la praticité et la stabilité. Souvent en cuir ou en daim, ce sont des escarpins à bout ronds ou carrés, des mocassins et des chaussures à lacet. Les babies et les salomés sont également d’époque.
			</p>
			<h3 style="font-weight: bold; color: white">
				Et maintenant on cherche où ?
			</h3>
			<p>
				Alors mes recommandations sont les suivantes : 
			</p>
			<ul style="color: white">
				<li>Top Vintage est le site de référence en tenues vintage. Vous pouvez même effectuer vos recherches par décennie. Cela vous permettra d’identifier des marques qui vous plaisent et de faire vos recherches sur Vinted si les prix sont trop élevés. </li>
				<li>Ma marque chouchoute est Voodoo Vixen, mais vous pourrez trouver chez collectif, Hellbunny, seamstress of bloomsburry, glamour bunny, et tant d’autres ! </li>
				<li>En toute honnêteté cette année vous pourrez également trouver sur des sites tels que Cider. </li>
			</ul>
			<p style="font-weight: bold">
				Quoi qu’il arrive n’hésitez pas à m’envoyer ce que vous avez repéré !
			</p>
			<h3 style="font-weight: bold; color: white">
				Et pour ces Messieurs ? 
			</h3>
			<p>
				Les pantalons larges étaient populaires, souvent associés à des vestes ajustées. Les hommes portaient également des chemises à col boutonné et des cravates étroites pour compléter leur tenue. Les chaussures en cuir étaient préférées et les chapeaux étaient également un accessoire courant.
			</p>
			</div>
			<div class="_footer">
				<button class="link" on:click="{() => opened = !opened}">{opened ? 'Voir moins' : 'Lire plus'}</button>
			</div>
		</div>

		<div class="code" id="mairie" style="background: rgb(197 103 103);">
			<h1>Mairie, 13h30</h1>
			<p>Mairie de Douai 83 Rue de la Mairie, 59500 Douai</p>
			<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2544.9390057587643!2d3.0805721999999998!3d50.367691799999996!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47c2c967c812a74f%3A0x3955107e8d5a47a2!2sMairie%20de%20Douai!5e0!3m2!1sfr!2sfr!4v1727466178463!5m2!1sfr!2sfr" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
		</div>

		<div class="code" id="vin" style="background: rgb(197 103 103);">
			<h1>Vin d'honneur, 16h</h1>
			<p>La Belle Grange 751 Bernstraete, 59270 Bailleul</p>
			<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2526.78350911202!2d2.6827663767118977!3d50.705401868973794!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47dcdf7f7fea7c77%3A0xa722ce9ba7ca02f9!2sLa%20Belle%20Grange!5e0!3m2!1sfr!2sfr!4v1727466332357!5m2!1sfr!2sfr" width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
		</div>
	
		<div class="code" id="musique"  style="background: rgb(197 103 103);">
			<h1>Envie de musique ?</h1>
			<p>Nous ne prendrons probablement pas en compte toutes vos demandes, mais qui sait ?</p>
			<form action="mailto:vzwed2025@gmail.com" method="post" enctype="text/plain">
		
				<textarea name="tracks" style="width: 100%; height: 160px" 
				placeholder="{'artiste:titre\nartiste:titre\n...'}"></textarea><br>
				
				<input type="submit" value="Send">
			</form>
		</div>

	</div>
</section>

<audio id="musicplayer" autoplay style="visibility: hidden;">
	<source src="{dance}" />
</audio>

<style lang="scss">
	* {
		font-family: "Roboto", serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		font-variation-settings: "wdth" 100;
	}

	.hero {
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
		height: 90dvh;
		width: 100dvw;

		img {
			height: 100%;
		}
	}

	.hero_title {
		font-size: 4rem;
		margin-top: -10rem;
		h1 {
			font-family: "Playwrite VN", serif !important;
			font-optical-sizing: auto;
			font-weight: 400;
			font-style: normal;
			padding: 0;
			margin: 0;
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
	
		padding: 2rem;
		box-sizing: border-box;
		font-size: 1.2rem;

		h1 {
			font-family: "Playwrite VN", serif !important;
			font-optical-sizing: auto;
			font-weight: 400;
			font-style: normal;
		}

		._content:not(.opened){
			overflow: hidden;
			max-height: 200px;
			transition: max-height 0.2s ease-out;
			text-overflow: ellipsis;
		
		}
		
		._footer {
			display: flex;
			justify-content: center;
			padding: 1rem;

			button.link {
				background: none;
				border: none;
				border-bottom: 1px solid white;
				color: white;
				cursor: pointer;
				font-size: 2rem;
			}
		}

		button:not(.link), input {
			background-color: var(--primary);
			border-radius: 8px;
			border-style: none;
			box-sizing: border-box;
			color: #FFFFFF;
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

		button:hover,
		button:focus {
			background-color: #F082AC;
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

	h1, p {
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
		--primary: rgba(37, 37, 37, 1.0);
		--secondary: rgba(252, 41, 74, 1.0);
		--shades: rgba(238, 238, 238, 1.0);
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
		padding-top: .5em;
		padding-bottom: .5em;
		background-color: var(--primary);
		-webkit-box-shadow: 0 14px 14px -14px rgba(0, 0, 0, .75);
		-moz-box-shadow: 0 14px 14px -14px rgba(0, 0, 0, .75);
		box-shadow: 0 14px 14px -14px rgba(0, 0, 0, .75);
	}

	.sticky {
		position: -webkit-sticky;
		position: sticky;
		top: 0;
		z-index: 1;
	}

	.hidden {
		display: none;
	}

	.display__logo {
		font-size: 2.5rem;
		margin-bottom: .5rem;
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
		padding-top: .3125rem;
		padding-bottom: .3125rem;
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

	@media screen and (max-width: 799px) {
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


	#nav:checked+.nav__open {
		transform: rotate(45deg);
	}

	#nav:checked+.nav__open i {
		background-color: var(--shades);
		transition: transform 0.2s ease;
	}

	#nav:checked+.nav__open i:nth-child(1) {
		transform: translateY(6px) rotate(180deg);
	}

	#nav:checked+.nav__open i:nth-child(2) {
		opacity: 0;
	}

	#nav:checked~.nav__item a {
		display: block !important;
	}

	#nav:checked+.nav__open i:nth-child(3) {
		transform: translateY(-6px) rotate(90deg);
	}

	#nav:checked~.nav {
		z-index: 9990;
		opacity: 1;
		left: 0;
	}

	#nav:checked~.nav ul li a {
		opacity: 1;
		transform: translateY(0);
	}
		


</style>
