<script>
	import { onMount } from 'svelte';
	import Saos from 'saos';
	import headshot from '$lib/about/images/cropped_headshot.jpg';

	let isMobile = false;

	const checkScreenWidth = () => {
		isMobile = window.innerWidth <= 1000;
	};

	onMount(() => {
		checkScreenWidth();
		window.addEventListener('resize', checkScreenWidth);
	});
</script>

<div id="about">
<!--	<Saos-->
<!--		animation={isMobile-->
<!--    ? 'fade-in 0.5s ease-in-out both'-->
<!--    : 'fade-in 2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}-->
<!--		top={50}-->
<!--		bottom={50}-->
<!--		once={true}-->
<!--	>-->
<!--		<h1>Lillian Ho</h1>-->
<!--	</Saos>-->
	<div class="about-contents">
		<Saos
			animation={isMobile
				? 'fade-in 2s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'
				: 'slide-right 1s cubic-bezier(0.250, 0.460, 0.450, 0.940) both'}
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
			<h1>Lillian Ho</h1>
			<p id="about-paragraph">
				I'm a 4th year at UC San Diego majoring in computer science and cognitive science. I enjoy
				building impactful software and learning new technologies. In my free time, I enjoy
				collecting <a
					href="https://drive.google.com/file/d/1-Gd3B56djEqnLeEfg0hfezUSlxztz-ak/view?usp=sharing"
					target="_blank"
					rel="noopener noreferrer">Smiskis</a
				>, knitting, and going on long walks.
				<br />
				<br />
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
			margin-top: 5em;
	}

	.about-contents {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: row;
	}

	h1 {
		font-size: 4vw;
	}

	img {
		object-fit: cover;
		width: 20vw;
		height: 20vw;
		border-radius: 100%;
		padding-right: 10em;
	}

	p {
		width: 30em;
	}

	@media only screen and (max-width: 1000px) {
			#about {
					padding: 0;
			}

      #about-paragraph {
          width: 80%;
          text-align: center;
          margin: 0 auto;
      }

			.about-contents {
          flex-direction: column;
			}

			h1 {
					font-size: 10vw;
          text-align: center;
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
