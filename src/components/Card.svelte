<script>
	export let img = '';
	export let title = 'title';
	export let description = 'description of project';
	export let repoLink = 'repo.url/link';
	export let deployedLink = 'site.url/link';
</script>

<div>
	<img src={img} alt="screen shot of {title} running" />
	<div class="content">
		<h2>{title}</h2>
		<p>{description}</p>
		<a href={repoLink}><img src="https://raw.githubusercontent.com/devicons/devicon/1119b9f84c0290e0f0b38982099a2bd027a48bf1/icons/github/github-original.svg" alt="github link"/><span>GitHub</span></a>
		<a href={deployedLink}><img src="https://img.icons8.com/material-rounded/1x/globe.png" alt="web link" /><span>Visit</span></a>
	</div>
</div>

<style>
	div:not(.content) {
		width: 20em;
		display: flex;
		flex-direction: column;
		border-radius: 1rem;
		border: .1em solid var(--border-color);
		overflow: hidden;
	}

	img {
		width: 100%;
		height: 100%;
		flex-grow: 1;
		border-radius: .5em .5em 0 0;
		border-bottom: .1em solid var(--border-color);
	}

	.content {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		padding-top: 0.5em;
		row-gap: .5em;
	}

	.content *:not(a) {
		grid-column: span 2;
	}

	h2, p {
		padding-inline: 1.5em;
	}

	h2 {
		font-family: var(--title-font);
		text-align: center;
	}

	p {
		font-family: var(--main-font);
		display: -webkit-inline-box;
		-webkit-box-orient: vertical;
		-webkit-line-clamp: 2;
		overflow: hidden;
	}

	a {
		font-family: var(--main-font);
		border-top: .1em solid var(--border-color);
		justify-self: center;
		background-color: var(--alt-color);
		color: var(--alt-text-color);
		width: 100%;
		text-align: center;
		padding-block: .5em;
		display: flex;
		align-content: center;
		justify-content: center;
		gap: .5rem;
		text-decoration: none;
	}

	a:first-of-type {
		border-right: .05em solid var(--border-color);
	}

	a:last-of-type {
		border-left: .05em solid var(--border-color);
	}

	a:where(:focus-visible, :hover) {
		background-color: var(--main-color);
		color: var(--main-text-color);
	}

	a > span {
		text-decoration: underline;
	}

	a:where(:hover, :focus-visible) > span {
		text-decoration: none;
	}

	a > img {
		--img-size: 1em;
		max-height: var(--img-size);
		max-width: var(--img-size);;
		border: none;
	}

	a:where(:hover, :focus-visible) > img {
		filter: invert(100%);
	}
</style>
