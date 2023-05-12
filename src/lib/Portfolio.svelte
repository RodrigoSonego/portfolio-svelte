<script>
	import { fade, fly } from "svelte/transition";
	import { onMount } from "svelte";

	import logoCiencias from "../assets/LogoCiencias.png";
	import logoCorpoHumano from "../assets/LogoCorpo.png";
	import logoMatematica from "../assets/LogoMatematica.png";
	import logoGeografia from "../assets/LogoGeografia.png";
	import logoUniverso from "../assets/LogoUniverso.png";
	import logoDicestDungeon from "../assets/dicestDungeon.png"

	import googlePlay from "../assets/googleplay.png";
	import itchButton from "../assets/itch.png";
	import githubButton from "../assets/github_avail.png";

	import dicestPreview from "../assets/dicestDungeon.gif"

	import CollapsibleSection from "./CollapsibleSection.svelte";
    import PublicationButton from "./PublicationButton.svelte";

	const cienciasLink =
		"https://play.google.com/store/apps/details?id=com.LionStudios.Ciencia";
	const matematicaLink =
		"https://play.google.com/store/apps/details?id=br.com.lionstudios.matematicara";
	const corpoHumanoLink =
		"https://play.google.com/store/apps/details?id=com.LionStudios.LCHRA";
	const geografiaLink =
		"https://play.google.com/store/apps/details?id=com.DefaultCompany.Geografia";
	const universoLink =
		"https://play.google.com/store/apps/details?id=com.Lion.Universo";
	const dicestItchLink = 
		"https://fufumiga.itch.io/dicest-dungeon";
	const dicestGitLink = 
		"https://github.com/RodrigoSonego/dicest-dungeon";


	let cienciasSection;
	let matSection;
	let corpoSection;
	let geoSection;
	let universoSection;

	let hasCienciasAppeared = false;
	let hasMatematicaAppeared = false;
	let hasCorpoAppeared = false;
	let hasGeoAppeared = false;
	let hasUniversoAppeared = false;

	onMount(() => {
		cienciasSection = document.getElementById("ciencias");
		matSection = document.getElementById("matematica");
		corpoSection = document.getElementById("corpohumano");
		geoSection = document.getElementById("geografia");
		universoSection = document.getElementById("universo");
	});

	function hasEnteredViewport(element) {
		const rect = element.getBoundingClientRect();
		const offset = rect.height / 2; // considera no viewport a partir da metade do elemento

		return (
			rect.top >= 0 &&
			rect.left >= 0 &&
			rect.bottom <=
				(window.innerHeight + offset ||
					document.documentElement.clientHeight + offset) &&
			rect.right <=
				(window.innerWidth || document.documentElement.clientWidth)
		);
	}

	function checkIfElementsEnteredViewport() {
		if (hasCienciasAppeared === false) {
			hasCienciasAppeared = hasEnteredViewport(cienciasSection);
		}
		if (hasMatematicaAppeared === false) {
			hasMatematicaAppeared = hasEnteredViewport(matSection);
		}
		if (hasCorpoAppeared === false) {
			hasCorpoAppeared = hasEnteredViewport(corpoSection);
		}
		if (hasGeoAppeared === false) {
			hasGeoAppeared = hasEnteredViewport(geoSection);
		}
		if (hasUniversoAppeared === false) {
			hasUniversoAppeared = hasEnteredViewport(universoSection);
		}
	}

	document.addEventListener("scroll", checkIfElementsEnteredViewport);

	console.log(window.innerWidth);
</script>

<link
	href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
	rel="stylesheet"
	integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
	crossorigin="anonymous"
/>

<div class="bg-light d-flex justify-content-center" id="portfolio">
	<div class="about-container container">
		<p />
		<h1 class="flex-block text-center title">
			<strong> Meu Trabalho </strong>
		</h1>
		<hr />
		<div id="ciencias">
			<CollapsibleSection headerText="Ciências RA" iconSrc={logoCiencias}>
				<div class="work-info-container">
					<h3>Sobre</h3>
					<p>
						Ciências RA é um aplicativo de realidade aumentada usado para
						auxiliar no aprendizado do conteúdo de Ciências do Ensino Fundamental
					</p>
					<h3>Tecnologias usadas</h3>
						<ul>
							<li>Unity</li>
							<li>C# (.NET)</li>
							<li>EasyAR SDK</li>
						</ul>

					<h3>Responsabilidades</h3> 
						<ul>
							<li>Desenvolvimento de novas cenas</li>
							<li>Implementação de UI responsiva</li>
							<li>Publicação para Android</li>
						</ul>
					
					<h3>Publicação</h3>
					<PublicationButton imgSrc={googlePlay} publicationUrl={cienciasLink} />
				</div>
			</CollapsibleSection>
		</div>
		<hr />
		<div id="dicestDungeon">
			<CollapsibleSection headerText="Dicest Dungeon" iconSrc={logoDicestDungeon}>
				<div class="work-info-container">
					<h3>Sobre</h3>
					<p>
						Um jogo de combate baseado em turnos feito em 48 horas como entrada para a
						GMTK Game Jam 2022, com o tema de "Roll of The Dice".
						<br>
						Baseado em Darkest Dungeon, o jogador deve andar pelo cassino e lutar contra
						os inimigos em batalhas por turno rolando diferentes dados para determinar o dano causado.
						<br>
						Arte por <a href="https://www.linkedin.com/in/paulo-victor-a1648724a/">Paulo Victor</a>
					</p>
					<h3>Publicação</h3>
					<PublicationButton imgSrc={itchButton} publicationUrl={dicestItchLink}/>
					<PublicationButton imgSrc={githubButton} publicationUrl={dicestGitLink} />
					<p/>
					<h3>Galeria</h3>
					<div class="preview-container">
						<img src={dicestPreview} alt="DicestDungeon" height="400rem" width="auto">
						<span class="caption">Menu de combate</span>
					</div>
				</div>
			</CollapsibleSection>
		</div>
	</div>
</div>

<style>
	.title {
		padding-top: 20px;
		margin-bottom: 20px;
	}

	@media (min-width: 600px) {
		.about-container {
			padding-left: 24px;
			padding-right: 24px;
			padding-bottom: 5%;
			max-width: 85%;
		}
	}

	.work-info-container {
		padding: 1rem 0;
		font-size: 1.3rem;
		font-weight: 400;

		margin-right: 3%;
		margin-left: 3%;
	}

	p {
		padding-left: 1.5rem;
	}

	.preview-container {
		margin-top: 1rem;
		display: flexbox;
		justify-content: center;
		text-align: center;
	}

	.caption {
		display: block;
		font-size: 1.3rem;
	}
</style>
