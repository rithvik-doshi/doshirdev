<script>
	import { page } from '$app/stores';
	import logo from '$lib/images/favicon.png';
	import eng_logo from '$lib/images/favicon_eng.png'
	import github from '$lib/images/github.svg';
	import { delay } from "./delay";
	let titles = ["ऋत्विक दोशी", "Rithvik Doshi"];
  	let langs = ["Hindi", "English"];

	let outlogo = logo;
	let logolang = true;
	let title = titles[0];
	let lang = langs[0];

	const switchImg = async () => {
		logolang = !logolang
		outlogo = logolang ? logo : eng_logo;
		title = logolang ? titles[1] : titles[0];
		lang = logolang ? langs[1] : langs[0];
		console.log(title, lang);
	}

</script>

<header>
	<div class="corner">
		<div>
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<img src={outlogo} alt="bruhmonguslogo" on:click={switchImg} />
		</div>
	</div>

	<nav>
		<svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L1,2 C1.5,3 1.5,3 2,3 L2,0 Z" />
		</svg>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Home</a>
			</li>
			<li aria-current={$page.url.pathname === '/about' ? 'page' : undefined}>
				<a href="/about">About</a>
			</li>
			<li aria-current={$page.url.pathname === '/courses' ? 'page' : undefined}>
				<a href="/courses">Courses</a>
			</li>
			<li aria-current={$page.url.pathname === '/writing' ? 'page' : undefined}>
				<a href="/writing">Writing</a>
			</li>
			<li aria-current={$page.url.pathname === '/coding' ? 'page' : undefined}>
				<a href="/coding">Coding</a>
			</li>
			<li aria-current={$page.url.pathname === '/music' ? 'page' : undefined}>
				<a href="/music">Music</a>
			</li>
			<!-- <li aria-current={$page.url.pathname.startsWith('/sverdle') ? 'page' : undefined}>
				<a href="/sverdle">Sverdle</a>
			</li> -->
		</ul>
		<svg viewBox="0 0 2 3" aria-hidden="true">
			<path d="M0,0 L0,3 C0.5,3 0.5,3 1,2 L2,0 Z" />
		</svg>
	</nav>

	<div class="corner">
		<a href="https://github.com/rithvik-doshi" target="_blank" rel="noopener noreferrer">
			<img src={github} alt="GitHub" />
		</a>
	</div>
</header>

<style>
	header {
		display: flex;
		justify-content: space-between;
	}

	.corner {
		width: 5em;
		height: 5em;
	}

	.corner a {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner div {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
	}

	.corner img {
		width: 4em;
		height: 4em;
		object-fit: contain;
	}

	.Hindi {
    	font-family: "Modak";
  	}

	nav {
		display: flex;
		justify-content: center;
		--background: rgba(255, 255, 255, 0.7);
	}

	svg {
		width: 2em;
		height: 3em;
		display: block;
	}

	path {
		fill: var(--background);
	}

	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
		background: var(--background);
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	li[aria-current='page']::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--color-theme-1);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		color: var(--color-text);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--color-theme-1);
	}
</style>
