<script lang="ts">
	import Carousel from 'svelte-light-carousel';
	import welcome from '$lib/images/us-home.jpg';
	import dance from '$lib/sound/dance.mp3';

	let dressCode: HTMLDivElement;
	let navOpen: HTMLInputElement;
	let fullPic: HTMLDivElement;
	let womenImg: string[] = [];
	let menImg: string[] = [];
	let videos: {id: string, type: 'tiktok' | 'youtube'}[] = [
		{id: '7429837847928114475', type: 'tiktok'},
		{id: '7383809111571352878', type: 'tiktok'},
		{id: '7089084396082302214', type: 'tiktok'},
		{id: 'https://www.youtube.com/embed/lyuFLU2Zqz0?si=TPSUnCimUlDR5Nr7', type: 'youtube'},
	];

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

	<input type="checkbox" id="nav" bind:this={navOpen} class="hidden" />
	<label for="nav" class="nav__open"><i></i><i></i><i></i></label>
	<div class="nav">
		<ul class="nav__items">
			<li class="nav__item">
				<a href="#dress-code" class="nav__link" on:click={() => (navOpen.checked = false)}
					>Dress code</a
				>
			</li>
			<li class="nav__item">
				<a href="#mairie" class="nav__link" on:click={() => (navOpen.checked = false)}>Mairie</a>
			</li>
			<li class="nav__item">
				<a href="#vin" class="nav__link" on:click={() => (navOpen.checked = false)}>Vin d'honneur</a
				>
			</li>
			<li class="nav__item">
				<a href="#musique" class="nav__link" on:click={() => (navOpen.checked = false)}>Musique ?</a
				>
			</li>
		</ul>
	</div>
</nav>

<section class="section section--code">
	<div class="container">
		<div class="code" id="dress-code" style="background: #70162e;" bind:this={dressCode}>
			<h1 style="text-align: center">Le dress code: années 40 !</h1>
			<p style="text-align: center">
				On vous rassure, notre mariage n’est pas un rassemblement historique ! On ne vous demande
				pas de courir les friperies afin de trouver le graal.
			</p>
			<p style="text-align: center">
				Toutefois, cela nous tient véritablement à cœur que chacun d’entre vous colle au thème.
			</p>
			<div class="_content" class:opened={women} id="women-content">
				<h3
					class="classy"
					id="robes-et-jupes"
					style="font-weight: bold; color: white; text-align: center"
				>
					Robes et jupes
				</h3>
				<p>
					Les robes des années 40 sont pensées pour mettre en avant la silhouette féminine. Cintrées
					à la taille et souvent accompagnées d’une ceinture, elles s’arrêtent sous le genou. Les
					jupes peuvent être évasées ou droites, ce sont les fameuses jupes crayons ! Les tailleurs
					jupes sont alors très populaires.
				</p>
				<p>
					Avec la guerre, les tenues deviennent plus fonctionnelles. Les vestes arborent des épaules
					carrées, et les jupes crayons, près du corps, gagnent en popularité. La robe chemisier est
					un indispensable, marquant la taille grâce à une ceinture. La robe Kitty Foyle est
					populaire : longueur au genou, base foncée, boutonnée et col plus clair, contrasté. Les
					jupes plissées sont également populaires.
				</p>
				<p>
					Après la guerre, le glamour revient en force avec des tailles cintrées et des jupes
					amples, donnant naissance à la silhouette sablier. Dior introduit les épaules rondes.
					Inspirée d&#39;Hollywood, la mode adopte des matières élégantes comme le velours, le satin
					et même des touches de paillettes. Couleurs vives et motifs audacieux, tout est redevenu
					possible.
				</p>
				<h3
					class="classy"
					id="hauts-et-vestes"
					style="font-weight: bold; color: white; text-align: center"
				>
					Hauts et vestes
				</h3>
				<p>
					Les blouses à boutons ou à col lavallière sont incontournables pour compléter une tenue
					élégante. Elles se marient parfaitement avec des vestes cintrées qui structurent la
					silhouette. Les cardigans courts et boléros apportent une touche raffinée et restent très
					populaires.
				</p>
				<h3
					class="classy"
					id="pantalons"
					style="font-weight: bold; color: white; text-align: center"
				>
					Pantalons
				</h3>
				<p>
					Si les robes et jupes dominent, certaines femmes adoptent le pantalon large à taille
					haute, inspiré du vestiaire masculin. Les &quot;pantalons à la française&quot;, aux jambes
					extra larges, font leur apparition, offrant une alternative élégante et confortable.
				</p>
				<p>Et si vous avez envie de vous la jouer star Hollywoodienne ?</p>
				<p>
					Dans ce cas, sortez vos gants de velours, le satin et les paillettes ! Les stars de la
					décennie sont Katharine Hepburn, Elizabeth Taylor, Rita Hayworth, Veronica Lake, Lauren
					Bacall et Ingrid Bergman. Les robes sont de style grec, princesse ou encore portefeuille.
				</p>
				<h3
					class="classy"
					id="accessoires"
					style="font-weight: bold; color: white; text-align: center"
				>
					Accessoires
				</h3>
				<p>
					Les accessoires sont indispensables pour peaufiner le style. Les chapeaux comme les
					bérets, bibis ou turbans noués ajoutent une touche chic.
				</p>
				<p>
					Les gants en cuir ou en dentelle renforcent l’élégance, tout comme les bas à couture
					apparente. Pour les bijoux, on privilégie la sobriété avec des perles, des broches et des
					clips d’oreille. Les ceintures épaisses à grosse boucle marquent la taille avec style.
				</p>
				<p>Quant aux sacs, les modèles rigides ou les pochettes sont à privilégier.</p>
				<h3
					class="classy"
					id="chaussures"
					style="font-weight: bold; color: white; text-align: center"
				>
					Chaussures
				</h3>
				<p>
					Les escarpins à talon épais, les sandales compensées et les richelieus féminins restent
					des valeurs sûres. On voit aussi des babies et des salomés, souvent en cuir ou en daim,
					offrant praticité et stabilité.
				</p>

				<h3 class="classy" style="font-weight: bold; color: white; text-align:center;">
					Inspirations
				</h3>
				<div class="carousel-wrapper">
					<Carousel
						style="height:100%"
						containerClass={'px-10'}
						slides={womenImg}
						layout={{ default: 1 }}
						oneAtTime={true}
						autoPlay={5}
					>
						<div style="height:100%;" slot="slide" let:slide>
							<div
								style="background-image:url('{slide}');height: 100%;
    width: 100%;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;"
								on:click={() => {
									fullPic.style.backgroundImage = 'url(' + slide + ')';
									fullPic.style.display = 'block';
								}}
							/>
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

				<h3 class="classy" style="font-weight: bold; color: white; text-align:center;">
					Où acheter ?
				</h3>

				<h4 style="font-weight: bold; color: white;">Vêtements</h4>
				<ul>
					<li>
						<a href="https://topvintage.fr/fr/robes-grandes-taillese/annees-1940"
							>Robes grandes tailles années 40 | Je shoppe chez Topvintage</a
						>
					</li>
					<li>
						<a href="https://ellerebel.com/">Elle Rebel | Alternative Design House – ElleRebel</a>
					</li>
					<li><a href="https://poopidoo.be/fr/">PooPiDoo – Webshop</a></li>
					<li>
						<a href="https://www.rocknromancevintage.com/"
							>RocknRomance Vintage, True &amp; Authentic 1940s &amp; 1950s Styled Clothing – Rock n
							Romance</a
						>
					</li>
					<li>
						<a href="https://www.michelinepitt.com/">Micheline Pitt – Vixen by Micheline Pitt</a>
					</li>
					<li>
						<a href="https://ladysplendorclothing.com/"
							>Lady Splendor Clothing – LadySplendorClothing</a
						>
					</li>
					<li>
						<a href="https://www.missbamboo.co.uk/"
							>1940s &amp; 50s reproduction vintage clothing - missbamboo.co.uk</a
						>
					</li>
					<li>
						<a href="https://heartmycloset.me/"
							>Kate middleton dress, Swing Dresses - Vintage pencil 1950s Dresses – heartmycloset</a
						>
					</li>
					<li>
						<a href="https://www.heyday.co.uk/collections/all">Products – Heyday Vintage Style</a>
					</li>
					<li>
						<a
							href="https://www.unique-vintage.com/?ir_clickid=0QjRIUXTpxyKWKgQHx1AbSRGUks2CdVHSy750c0&amp;ir_cid=834&amp;ir_affid=39177&amp;utm_campaign=TEXT_LINK&amp;utm_medium=Vintage%20Dancer&amp;utm_source=ImpactRadius"
							>Vintage Clothing &amp; Dresses – Retro Clothing Styles | Unique Vintage</a
						>
					</li>
					<li>
						<a href="https://www.karinadresses.com/collections/wedding-guest-dresses"
							>Wedding Guest Dresses – karina dresses</a
						>
					</li>
					<li>
						<a
							href="https://www.etsy.com/shop/SwingbirdFashions?fbclid=IwAR0OyXrluP-oVdljvarFfmwbP41brKCnZ8R7b5zlFhTy3utvfRKY5XQe5OQ&amp;source=aw&amp;utm_source=affiliate_window&amp;utm_medium=affiliate&amp;utm_campaign=us_location_buyer&amp;utm_content=143113&amp;utm_term=0&amp;sv1=affiliate&amp;sv_campaign_id=143113&amp;awc=6220_1738665167_ee7804e893655139fb64c15debd94e53"
							>SwingbirdFashions - Etsy France</a
						>
					</li>
					<li>
						<a href="https://trashydiva.com/search?q=1940s&amp;type=product"
							>Search: 107 results found for &quot;1940s&quot;</a
						>
					</li>
					<li>
						<a href="https://modcloth.com/collections/special-occasion-dresses"
							>Special Occasion Dresses | ModCloth</a
						>
					</li>
					<li>
						<a href="https://deadlyisthefemale.com/"
							>Deadly Is The Female | Vintage Style Dresses, footwear and accessories</a
						>
					</li>
					<li>
						<a href="https://www.weekenddoll.co.uk/collections/1940s-fashion"
							>Vintage Dresses, Blouses, Tops and Skirts - 1940s | Weekend Doll</a
						>
					</li>
					<li>
						<a
							href="https://www.etsy.com/shop/missfortuneuk?source=aw&amp;utm_source=affiliate_window&amp;utm_medium=affiliate&amp;utm_campaign=us_location_buyer&amp;utm_content=143113&amp;utm_term=0&amp;sv1=affiliate&amp;sv_campaign_id=143113&amp;awc=6220_1738665218_375bf34805ad46986aac73a28a519fa0"
							>MissFortuneUK - Etsy France</a
						>
					</li>
					<li><a href="https://www.emmydesign.se/en/">emmydesign</a></li>
					<li>
						<a href="https://retrospecd.com/"
							>Retro Outfits | Retro Dresses | Retro Fashion | Retrospec&#39;d – Retrospec&#39;d
							Clothing</a
						>
					</li>
					<li>
						<a href="https://elisedesign.com.au/collections/dresses">Dresses – Elise Design</a>
					</li>
					<li>
						<a href="https://www.theprettydresscompany.com/"
							>The Pretty Dress Company | Designed &amp; made in the UK</a
						>
					</li>
					<li>
						<a
							href="https://www.etsy.com/shop/BloodyEdith?source=aw&amp;utm_source=affiliate_window&amp;utm_medium=affiliate&amp;utm_campaign=us_location_buyer&amp;utm_content=143113&amp;utm_term=0&amp;sv1=affiliate&amp;sv_campaign_id=143113&amp;awc=6220_1738665248_e5e31c1daea1a8eff5254fd072423c21"
							>BloodyEdith - Etsy France</a
						>
					</li>
					<li>
						<a href="https://www.vivienofholloway.com/"
							>1950s Dresses &amp; Clothing l Vivien of Holloway</a
						>
					</li>
					<li>
						<a href="https://palava.co/collections/womens-dresses"
							>Women&#39;s Vintage Style Dresses &amp; Jumpsuits | Made in England</a
						>
					</li>
					<li>
						<a href="https://www.thehouseoffoxy.com/"
							>The House of Foxy: Vintage style clothing from 1930s, 1940s to 1970s</a
						>
					</li>
					<li>
						<a href="https://www.cherryvelvetplus.com/collections/dresses"
							>Dresses – Cherry Velvet</a
						>
					</li>
					<li><a href="https://www.penahaus.com/">Penahaus</a></li>

					<li>
						<a href="https://revivalvintage.co.uk/"
							>Authentic Vintage Clothing | Revival Vintage – RevivalVintage (Si vous souhaitez
							acheter sur ce site pouvez-vous nous en informer ? Plusieurs éléments ont déjà été
							commandés par les proches de la mariée, si on peut éviter les doublons c’est mieux)</a
						>
					</li>
					<li>
						<a href="https://theseamstressofbloomsbury.co.uk/"
							>The Seamstress of Bloomsbury: 1940s Dresses &amp; Vintage Clothing</a
						>
					</li>
					<li>
						<a href="https://morellos-clothing.co.uk/"
							>Morellos | Classic Forties and Fifties Vintage Style Clothing</a
						>
					</li>
				</ul>

				<h4 style="font-weight: bold; color: white;">Chaussures</h4>

				<ul>
					<li>
						<a href="https://memery.eu/"
							>Vintage shoes - vintage inspired shoes and boots – memery</a
						>
					</li>
					<li>
						<a href="https://www.charliestoneshoes.com/en-fr"
							>Vintage style flats for easy and accessible elegance, everyday. – Charlie Stone</a
						>
					</li>
					<li>
						<a
							href="https://topvintage.fr/fr/chaussures?msclkid=13c859f65acf150bbde83e578d48d463&amp;utm_source=bing&amp;utm_medium=cpc&amp;utm_campaign=FR%20%7C%20Search%20%7C%20Subcategorie%20%7C%20Branded&amp;utm_term=topvintage%20chaussures&amp;utm_content=Chaussures"
							>Chaussures femme ? | Mode d’inspiration vintage | Topvintage</a
						>
					</li>
					<li>
						<a href="https://www.rocketoriginals.co.uk/"
							>Reproduction 1940s &amp; 1950s Shoes &amp; Clothing - Rocket Originals</a
						>
					</li>
					<li><a href="https://baitfootwear.com/">BAIT Footwear – B.A.I.T. Footwear</a></li>
					<li><a href="https://www.penahaus.com/">Penahaus</a></li>
					<li>
						<a href="https://www.lolaramona.com/collections/lola-ramona-shoes"
							>Lola Ramona Shoes - Lola Ramona</a
						>
					</li>
					<li>
						<a href="https://laveintinueve.com/fr/"
							>Chaussures Pin-up et vêtements rétro style pour votre look</a
						>
					</li>
				</ul>
			</div>
			<div class="_content" class:opened={men} id="men-content">
				<h3
					class="classy"
					id="costumes"
					style="font-weight: bold; color: white; text-align: center"
				>
					Costumes
				</h3>
				<p>
					Le costume est une pièce maîtresse du vestiaire masculin des années 40. Généralement en
					trois pièces, il est bien ajusté et met en avant des épaules structurées. Les couleurs
					restent sobres avec du gris, du marron ou du bleu marine, parfois agrémentées de motifs
					comme le tweed, les chevrons ou les larges rayures craie.
				</p>
				<p>
					Les restrictions de guerre ont imposé un certain minimalisme dans les costumes, limitant
					les gilets et favorisant des tissus mélangés avec de la rayonne.
				</p>
				<h3
					class="classy"
					id="pantalons"
					style="font-weight: bold; color: white; text-align: center"
				>
					Pantalons
				</h3>
				<p>
					Les pantalons de cette époque sont taille haute avec des pinces et des jambes droites,
					légèrement fuselées. Ils se portent volontiers avec des bretelles plutôt qu’une ceinture,
					renforçant ainsi le style vintage.
				</p>
				<h3
					class="classy"
					id="chemises-et-vestes"
					style="font-weight: bold; color: white; text-align: center"
				>
					Chemises et vestes
				</h3>
				<p>
					Les chemises blanches ou pastel à col en pointe sont des valeurs sûres. Elles
					s’accompagnent idéalement d’une cravate large aux motifs géométriques, floraux ou art
					déco. Les chemises colorées à rayures fines ou à pois sont aussi très tendance.
				</p>
				<p>
					Le gilet assorti au costume se fait plus rare en raison des restrictions, mais certains
					hommes l’adoptent encore. Pour les jours plus frais, un trench-coat ou un manteau long en
					laine sera parfait pour un look authentique.
				</p>
				<h3
					class="classy"
					id="accessoires"
					style="font-weight: bold; color: white; text-align: center"
				>
					Accessoires
				</h3>
				<p>
					Les chapeaux sont indispensables pour parfaire une tenue d’époque. Fedora, Trilby ou
					encore casquette plate s’accordent parfaitement au style des années 40.
				</p>
				<p>
					Les hommes complètent souvent leur tenue avec une montre de poche ou une montre-bracelet
					en cuir. Les bretelles larges sont encore d&#39;usage, bien que les ceintures prennent le
					pas. Les mouchoirs de poche en soie ou rayonne, souvent pliés en triangle, ajoutent une
					touche sophistiquée.
				</p>
				<h3
					class="classy"
					id="chaussures"
					style="font-weight: bold; color: white; text-align: center"
				>
					Chaussures
				</h3>
				<p>
					Pour finir la tenue avec élégance, les richelieus en cuir noir ou marron sont des valeurs
					sûres.
				</p>
				<p>
					Les derbies et mocassins sont également de bonnes options pour adopter un look chic et
					intemporel. Les chaussures bicolores Oxford gagnent en popularité, ajoutant une touche
					d’originalité.
				</p>

				<h3 class="classy" style="font-weight: bold; color: white; text-align:center;">
					Inspirations
				</h3>
				<div class="carousel-wrapper">
					<Carousel
						style="height:100%"
						containerClass={'px-10'}
						slides={menImg}
						layout={{ default: 1 }}
						oneAtTime={true}
						autoPlay={5}
					>
						<div style="height:100%;" slot="slide" let:slide>
							<div
								style="background-image:url('{slide}');height: 100%;
					width: 100%;
					background-size: contain;
					background-position: center;
					background-repeat: no-repeat;"
								on:click={() => {
									console.log('toto');
									fullPic.style.backgroundImage = 'url(' + slide + ')';
									fullPic.style.display = 'block';
								}}
							/>
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

				<h3 class="classy" style="font-weight: bold; color: white; text-align:center;">
					Où acheter ?
				</h3>

				<h4 style="font-weight: bold; color: white;">Vêtements</h4>
				<ul>
					<li>
						<a href="https://www.hockerty.fr/fr/"
							>Hockerty : Habillez votre authenticité en sur-mesure</a
						>
					</li>
					<li><a href="http://morellos-clothing.co.uk/">Morello’s Clothing</a></li>
					<li><a href="http://www.chestercordite.com/">Chester Cordite</a></li>
					<li>
						<a href="http://www.mapledoram.com/product-category/mens-gents-1940s/">Mapledoram</a>
					</li>
					<li><a href="http://www.darcyclothing.com/">Darcy Clothing</a></li>
					<li><a href="https://www.somelikeitholy.com/gentlemen-c-1.html">Some Like it Holy</a></li>
					<li><a href="http://www.vecona-vintage.com/">Vecona Vintage</a></li>
					<li><a href="http://www.heydayonline.co.uk/default/mens-clothing">Heyday!</a></li>
					<li><a href="http://www.juke-jive.de/">Juke Jive</a></li>
					<li>
						<a
							href="https://www.awin1.com/cread.php?awinmid=6220&amp;awinaffid=143113&amp;platform=dl&amp;ued=https%3A%2F%2Fwww.etsy.com%2Fshop%2FVivaLaRosaVintage%3Fref%3Dshop-header-name%26listing_id%3D1352778721%26from_page%3Dlisting"
							>Viva La Rose Vintage
						</a>
					</li>
					<li>
						<a href="http://www.onthesunnyside.nl">On the Sunny Side</a>
					</li>
					<li><a href="https://www.cousinjack.co.uk/">Cousin Jack</a></li>

					<li>
						<a href="https://revivalvintage.co.uk/"
							>Authentic Vintage Clothing | Revival Vintage – RevivalVintage (Si vous souhaitez
							acheter sur ce site pouvez-vous nous en informer ? Plusieurs éléments ont déjà été
							commandés par les proches de la mariée, si on peut éviter les doublons c’est mieux)</a
						>
					</li>
					<li>
						<a href="https://theseamstressofbloomsbury.co.uk/"
							>The Seamstress of Bloomsbury: 1940s Dresses &amp; Vintage Clothing</a
						>
					</li>
					<li>
						<a href="https://morellos-clothing.co.uk/"
							>Morellos | Classic Forties and Fifties Vintage Style Clothing</a
						>
					</li>
				</ul>

				<h4 style="font-weight: bold; color: white;">Chaussures</h4>

				<ul>
					<li><a href="https://remixvintageshoes.com/">ReMix Vintage</a></li>
					<li>
						<a href="https://www.johnstonmurphy.com/">Johnson and Murphy</a>
					</li>
					<li><a href="https://www.ghbass-eu.com/">G.H. Bass</a></li>
					<li>
						<a href="http://www.walkover.com">Walk-Over Vintage Collection</a>
					</li>
					<li><a href="http://www.civilwarboots.com/">Mattimore Boots</a></li>
					<li><a href="https://www.keds.com/">Keds</a></li>
					<li><a href="https://www.forzieri.com/mens-shoes/forzieri">Forzieri</a></li>
					<li><a href="https://www.madetomeasureshoes.com/">Made to measure shoes</a></li>
					<li><a href="http://www.harr-shoes.com/">Harr Shoes</a></li>
				</ul>
			</div>
			<div class="_footer">
				<button
					class="link"
					on:click={() => {
						men = false;
						women = !women;
						dressCode.scrollIntoView({ behavior: 'smooth' });
					}}>{women ? 'Voir moins' : 'Mesdames'}</button
				>
				<button
					class="link"
					on:click={() => {
						women = false;
						men = !men;
						dressCode.scrollIntoView({ behavior: 'smooth' });
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
			<h1>Cérémonie laïque, 15h30</h1>
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
			<h1>Let's danse ?</h1>
			<p>Apprenez quelques choré et dansez avec nous !</p>

			<Carousel
						style="height:100%"
						containerClass={'px-10'}
						slides={videos}
						layout={{ default: 1 }}
						oneAtTime={true}
					>
						<div style="height:100%; " slot="slide" let:slide>
							<div style="height: 100%; width: 100%; display: flex; justify-content: center;  align-items: center;">
								{#if slide.type === 'tiktok'}
									<blockquote
										class="tiktok-embed"
										data-video-id={slide.id}
										style="max-width: 605px;min-width: 325px; max-height: 619px;"
									>
									<section></section>
									</blockquote>
								{:else}
									<iframe width="560" height="315" src={slide.id} title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
								{/if}
							</div>
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
			
			<script async src="https://www.tiktok.com/embed.js"></script>
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

<div bind:this={fullPic} id="fullpage" on:click={() => (fullPic.style.display = 'none')}></div>

<style lang="scss">
	* {
		font-family: 'Roboto', serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		font-variation-settings: 'wdth' 100;
		--sc-color-rgb-light: rgb(255, 255, 255);
		--color-theme-1: #f7f7f7;
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
			gap: 2rem;

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
		transition: transform 0.4s ease-in-out;
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
		transition-property:
			color,
			background-color,
			border-color,
			text-decoration-color,
			fill,
			stroke,
			opacity,
			box-shadow,
			transform,
			filter,
			-webkit-backdrop-filter;
		transition-property: color, background-color, border-color, text-decoration-color, fill, stroke,
			opacity, box-shadow, transform, filter, backdrop-filter;
		transition-property:
			color,
			background-color,
			border-color,
			text-decoration-color,
			fill,
			stroke,
			opacity,
			box-shadow,
			transform,
			filter,
			backdrop-filter,
			-webkit-backdrop-filter;
		transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
		transition-timing-function: cubic-bezier(0, 0, 0.2, 1);
		transition-duration: 0.2s;
		border-radius: var(--rounded-btn, 0.5rem);
		height: 3rem;
		padding-left: 1rem;
		padding-right: 1rem;
		font-size: 0.875rem;
		line-height: 1.25rem;
		line-height: 1em;
		min-height: 3rem;
		gap: 0.5rem;
		font-weight: 600;
		text-decoration-line: none;
		border-width: var(--border-btn, 1px);
		animation: button-pop var(--animation-btn, 0.25s) ease-out;
		text-transform: var(--btn-text-case, uppercase);
		--tw-border-opacity: 1;
		--tw-bg-opacity: 1;
		background-color: hsl(var(--b2) / var(--tw-bg-opacity));
		--tw-text-opacity: 1;
		color: hsl(var(--bc) / var(--tw-text-opacity));
		outline-color: hsl(var(--bc) / 1);
	}

	.opacity-50 {
		opacity: 0.5;
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

	.aria-\[selected\=\"true\"\]\:bg-slate-100[aria-selected='true'] {
		--tw-bg-opacity: 1;
		background-color: rgb(241 245 249 / var(--tw-bg-opacity));
	}
	.aria-\[selected\=\"true\"\]\:scale-125[aria-selected='true'] {
		--tw-scale-x: 1.25;
		--tw-scale-y: 1.25;
		transform: translate(var(--tw-translate-x), var(--tw-translate-y)) rotate(var(--tw-rotate))
			skew(var(--tw-skew-x)) skewY(var(--tw-skew-y)) scaleX(var(--tw-scale-x))
			scaleY(var(--tw-scale-y));
	}
	.transition-all {
		transition-property: all;
		transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
		transition-duration: 0.15s;
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

	button,
	input,
	optgroup,
	select,
	textarea {
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

	button,
	[type='button'],
	[type='reset'],
	[type='submit'] {
		-webkit-appearance: button;
		background-color: transparent;
		background-image: none;
	}
	button,
	select {
		text-transform: none;
	}

	*,
	:before,
	:after {
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
			transform: scale(var(--btn-focus-scale, 0.98));
		}

		40% {
			transform: scale(1.02);
		}

		to {
			transform: scale(1);
		}
	}

	button:active:hover,
	.btn:active:focus {
		animation: button-pop 0s ease-out;
		transform: scale(var(--btn-focus-scale, 0.97));
	}

	.gap-2 {
		gap: 0.5rem;
	}
	.justify-center {
		justify-content: center;
	}
	.items-center {
		align-items: center;
	}

	.flex {
		display: flex;
	}
	.z-10 {
		z-index: 10;
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
		border-radius: 0.125rem;
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
		height: 0.5rem;
	}
	.flex {
		display: flex;
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
		transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
		transition-duration: 0.15s;
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

	h3.classy {
		text-align: center;
		font-size: 30px;
		font-weight: 300;
		color: #222;
		letter-spacing: 1px;
		text-transform: uppercase;

		display: grid;
		grid-template-columns: 1fr max-content 1fr;
		grid-template-rows: 27px 0;
		grid-gap: 20px;
		align-items: center;
	}

	h3.classy:after,
	h3.classy:before {
		content: ' ';
		display: block;
		border-bottom: 1px solid #f8f8f8;
		border-top: 1px solid #f8f8f8;
		height: 5px;
		//background-color:#f8f8f8;
	}

	ul {
		li {
			margin-bottom: 10px;
		}
	}

	@media screen and (max-width: 799px) {
		.carousel-wrapper {
			display: flex;
			justify-content: center;
			width: 100%;
		}

		.w-4 {
			width: 0.5rem;
		}
		.h-4 {
			height: 0.5rem;
		}

		.w-1\/2 {
			width: 100%;
		}

		.left-1\/4 {
			left: 0;
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
			top: 10px;
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
