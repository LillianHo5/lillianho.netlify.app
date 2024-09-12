<script>
	import Navbar from '$lib/navbar/navbar.svelte';
	import About from '$lib/about/about.svelte';
	import Experience from '$lib/experience/experience.svelte';

	import '../app.css';
</script>

<Navbar />
<About />
<Experience />

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
</style>
