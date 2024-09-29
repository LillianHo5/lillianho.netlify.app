<script>
	import LinkedIn from '$lib/components/linkedin.svelte';
	import GitHub from '$lib/components/github.svelte';
	import Mail from '$lib/components/mail.svelte';
	import Hamburger from '$lib/components/hamburger.svelte';

	let menuOpen = false;

	function toggleMenu() {
		menuOpen = !menuOpen;
	}

	function closeMenu() {
		menuOpen = false;
	}
</script>

<div class="desktop-navbar">
	<nav>
		<a href="/"><p>Home</p></a>
		<a href="#about"><p>About</p></a>
		<a href="#experience"><p>Experience</p></a>
		<a href="#education"><p>Education</p></a>
		<a
			href="https://drive.google.com/file/d/1wylxtFSm5GFTctFuN9c0RS3TPVtdrrUK/view?usp=sharing"
			target="_blank"><p>Resume</p></a
		>
		<a href="mailto:holillian8@gmail.com"><Mail fill="#EDF1D6" /></a>
		<a href="https://www.linkedin.com/in/lillianmho/" target="_blank"><LinkedIn fill="#EDF1D6" /></a
		>
		<a href="https://github.com/lillianho5" target="_blank"><GitHub fill="#EDF1D6" /></a>
	</nav>
</div>

<div class="mobile-navbar">
	<div class="navbar-header">
		<button class="hamburger-button" on:click={toggleMenu}>
			<Hamburger fill="#EDF1D6" />
		</button>
	</div>
	{#if menuOpen}
		<ul class="mobile-menu">
			<li><a href="/" on:click={closeMenu}><p>Home</p></a></li>
			<li><a href="#about" on:click={closeMenu}><p>About</p></a></li>
			<li><a href="#experience" on:click={closeMenu}><p>Experience</p></a></li>
			<li><a href="#education" on:click={closeMenu}><p>Education</p></a></li>
			<li>
				<a
					href="https://drive.google.com/file/d/1Oc2tLSkskX7b2g4yVCUOYE4DxeoSET-t/view?usp=sharing"
					target="_blank"
					on:click={closeMenu}><p>Resume</p></a
				>
			</li>
			<li><a href="mailto:holillian8@gmail.com" on:click={closeMenu}><p>Contact</p></a></li>
			<li>
				<a href="https://www.linkedin.com/in/lillianmho/" target="_blank" on:click={closeMenu}
					><p>LinkedIn</p></a
				>
			</li>
			<li>
				<a href="https://github.com/lillianho5" target="_blank" on:click={closeMenu}
					><p>GitHub</p></a
				>
			</li>
		</ul>
	{/if}
</div>

<style>
	nav {
		display: flex;
		justify-content: end;
		align-items: center;
	}

	.desktop-navbar {
		background-color: #609966;
		padding: 1rem;
	}

	a {
		margin: 0rem 2rem;
		text-decoration: none;
	}

	p {
		line-height: 0%;
		color: #edf1d6;
	}

	a:hover {
		font-weight: bold;
	}

	.mobile-navbar {
		display: none;
	}

	.navbar-header {
		background-color: #609966;
		padding: 0.5rem;
		display: flex;
		justify-content: flex-end;
	}

	.hamburger-button {
		background: none;
		border: none;
		cursor: pointer;
	}

	.mobile-menu {
		z-index: 100;
		list-style: none;
		padding: 0;
		margin: 0;
		background-color: #40513b;
		position: absolute;
		top: 8vw;
		left: 0;
		right: 0;
		width: 100%;
	}

	.mobile-menu li {
		padding: 1vw;
		border-bottom: 1px solid #edf1d6;
	}

	.mobile-menu a {
		color: #edf1d6;
		text-decoration: none;
		display: block;
	}

	.mobile-menu a:hover {
		font-weight: bold;
	}

	.mobile-menu p {
		font-size: 16px;
	}

	@media only screen and (max-width: 1000px) {
		.desktop-navbar {
			display: none;
		}

		.mobile-navbar {
			display: block;
		}
	}
</style>
