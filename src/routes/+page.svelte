<script>
	import Navbar from '$lib/navbar/navbar.svelte';
	import About from '$lib/about/about.svelte';
	import Experience from '$lib/experience/experience.svelte';
	import Education from '$lib/education/education.svelte';

	import '../app.css';
</script>

<div>
	<Navbar />
	<About />
	<Experience />
	<Education />
</div>

<svelte:head>
	<title>Lillian Ho</title>
	<meta name="description" content="Lillian Ho's personal website." />
</svelte:head>

<style global>
	@font-face {
		font-family: 'Poppins';
		font-style: normal;
		font-weight: normal;
		src: url(/fonts/Poppins-Medium.ttf);
	}

	@font-face {
		font-family: 'Poppins';
		font-style: normal;
		font-weight: bold;
		src: url(/fonts/Poppins-Bold.ttf);
	}

	@font-face {
		font-family: 'Roboto';
		font-style: normal;
		font-weight: normal;
		src: url(/fonts/Roboto-Medium.ttf);
	}

	@keyframes -global-fade-in {
		0% {
			opacity: 0;
		}
		100% {
			opacity: 1;
		}
	}

	@keyframes -global-slide-out-fwd-center {
		0% {
			transform: translateZ(1);
			opacity: 1;
		}
		100% {
			transform: translateZ(600px);
			opacity: 0;
		}
	}

	@keyframes -global-slide-right {
		0% {
			-webkit-transform: translateX(0);
			transform: translateX(0);
		}
		100% {
			-webkit-transform: translateX(100px);
			transform: translateX(100px);
		}
	}
</style>
