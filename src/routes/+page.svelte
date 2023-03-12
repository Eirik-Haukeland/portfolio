<script>
	import Card from '../components/Card.svelte';
	import scienceImg from '../assets/img/communityScienceMuseum.webp';
	import gameHubImg from '../assets/img/gamehub.webp';
	import hebsRecipesImg from "../assets/img/hebsRecipes.webp";
	import Title from "../components/Title.svelte";

	const projects = [
		{
			img: gameHubImg,
			title: 'GameHub',
			description: 'game store on line. That fetches data form a wordpress api with functionality to add product to a cart as well as sending in a message',
			repoLink: 'https://github.com/Noroff-FEU-Assignments/cross-course-project-Eirik-Haukeland',
			deployedLink: 'https://fantastic-pegasus-1d8ebd.netlify.app/'
		},
		{
			img: hebsRecipesImg,
			title: "Heb's Recipes",
			description: 'cooking blog site. Recipes are added on a wordpress server and fetched on load. This page has the ability to search for recipes and filter recipes by tag which are populated form the recipes.',
			repoLink: 'https://github.com/Noroff-FEU-Assignments/project-exam-1-Eirik-Haukeland',
			deployedLink: 'https://joyful-halva-a4d44f.netlify.app/index.html'
		},
		{
			img: scienceImg,
			title: 'Museum Site',
			description: 'Community Science Museum. This is a static site that are written in pure javascript, Html and Css.',
			repoLink: 'https://github.com/Eirik-Haukeland/Semester-Project-1',
			deployedLink: 'https://brilliant-blancmange-0b76a9.netlify.app/'
		}
	];
</script>

<Title pageTitle="Welcome to my portfolio site" />

<section aria-label="project cards">
	{#each projects as project}
		<Card {...project} />
	{/each}
</section>

<style>
	section {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 1em;
	}

	@media screen and (max-width: 1000px) {
		section{
			grid-template-columns: repeat(2, 1fr);
		}
	}

	@media screen and (max-width: 700px) {
		section{
			grid-template-columns: 1fr;
		}
	}
</style>
