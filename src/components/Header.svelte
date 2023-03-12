<script>
	import { onMount } from "svelte";
	import logo from "../assets/img/logo-white.svg"
	import menuIsOpen from "../assets/img/menu-open-white.svg"
	import menuIsClosed from "../assets/img/menu-closed-white.svg"
	import {page} from "$app/stores";

	let isMenuOpen = false;
	let windowLargerThan700 = false;

	let headerHeight = "0px";

	const closeMenuOnNavigation = () => isMenuOpen = false;

	let nav
	let menuBtn

	onMount(() => {
		windowLargerThan700 = window.innerWidth > 700;

		const header = document.querySelector("header");
		headerHeight = `${parseInt(getComputedStyle(header).getPropertyValue("height"))}px`;

		window.addEventListener("resize", () => windowLargerThan700 = window.innerWidth > 700);
		window.addEventListener("click", (e) => {
			if (isMenuOpen && !(menuBtn.contains(e.target) || menuBtn === e.target) ) {
				isMenuOpen = nav.contains(e.target)
			}
		});
	})

</script>

<header>
	<a href="/"><img src={logo} alt="return to home" /></a>
	<nav bind:this={nav}>
		<button hidden={windowLargerThan700}  id="menuBtn" bind:this={menuBtn} on:click={() => isMenuOpen = !isMenuOpen}>
			<img src={(isMenuOpen) ? menuIsOpen : menuIsClosed} alt={(isMenuOpen) ? "Close the menu" : "Open the menu"}>
		</button>
		<ul style='--header-height:{headerHeight}' hidden={!isMenuOpen && !windowLargerThan700}>
			<li>
				<a on:click={closeMenuOnNavigation} aria-current={$page.url.pathname === "/" ? "page" : undefined} href="/">Home</a>
			</li>
			<li>
				<a on:click={closeMenuOnNavigation} aria-current={$page.url.pathname === "/about" ? "page" : undefined} href="/about">bout</a>
			</li>
		</ul>
	</nav>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-inline: 5rem;
		padding-block: 1rem;
		background-color: var(--main-color);
	}

	#menuBtn {
		border: none;
		background-color: unset;
	}

	nav ul {
		display: flex;
		gap: 0.5rem;
		list-style: none;
		font-size: 1.5rem;
	}

	nav li {
		justify-self: center;
	}

	nav a {
		font-family: var(--main-font);
		color: var(--main-text-color);
		padding: 0.5rem;
		border-radius: 0.5rem;
	}

	nav a:is(:hover, :focus-visible, [aria-current="page"]) {
		background-color: var(--alt-color);
		color: var(--alt-text-color);
		text-decoration: none;
	}

	@media screen and (max-width: 700px) {
		header {
			position: sticky;
			top: 0;
			padding-inline: 1rem;
		}

		#menuBtn + ul:not([hidden]) {
			position: absolute;
			top: var(--header-height);
			right: 0;

			flex-direction: column;
			gap: 1.5rem;

			background-color: var(--main-color);
			padding: 1rem;
			padding-bottom: 1.5rem;

			border-radius: 0 0 0 .5rem;
		}
	}

	*[hidden] {
		display: none;
	}
</style>
