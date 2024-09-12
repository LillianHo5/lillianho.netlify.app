<script>
	import { onMount } from 'svelte';
	import Saos from 'saos';
	import headshot from '$lib/about/images/cropped_headshot.jpg';

	let isMobile = false;

	onMount(() => {
		const checkScreenWidth = () => {
			isMobile = window.innerWidth <= 1000;
		};

		checkScreenWidth();
	});
</script>

<div id="about">
	{#if isMobile}
		<h1>Lillian Ho</h1>
	{:else}
		<Saos
			animation={'fade-in 2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
			top={250}
			bottom={250}
			once={true}
		>
			<h1>Lillian Ho</h1>
		</Saos>
	{/if}
	<div class="about-contents">
		<Saos
			animation={isMobile ? '' : 'slide-right 1s cubic-bezier(0.250, 0.460, 0.450, 0.940) both'}
			top={250}
			bottom={250}
			once={true}
		>
			<img class="img" src={headshot} alt="Lillian Ho Headshot" />
		</Saos>
		<Saos
			animation={'fade-in 2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
			top={250}
			bottom={250}
			once={true}
		>
			<p>
				I'm an incoming 4th year at UC San Diego majoring in computer science and cognitive science.
				I enjoy building impactful software and learning new technologies. In my free time, I enjoy
				collecting Smiskis, knitting, and going on long walks.
				<br />
				<br /> I'm actively looking for new grad software engineering roles and off-season internships,
				and I'm always looking to take on new challenges. Feel free to reach out via email or LinkedIn!
			</p>
		</Saos>
	</div>
</div>

<style>
	#about {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
	}

	.about-contents {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: row;
	}

	h1 {
		font-size: 5vw;
	}

	img {
		object-fit: cover;
		width: 23vw;
		height: 23vw;
		border-radius: 100%;
		padding-right: 10em;
	}

	p {
		width: 30em;
	}

	@media only screen and (max-width: 1000px) {
		#about {
			padding: 0em;
		}

		.about-contents {
			flex-direction: column;
		}

		h1 {
			font-size: 10vw;
		}

		img {
			width: 40vw;
			height: 40vw;
			padding-right: 0em;
		}

		p {
			font-size: 16px;
			width: 20em;
		}
	}
</style>
