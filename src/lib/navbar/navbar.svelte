<script>
	import LinkedIn from '$lib/components/linkedin.svelte';
	import GitHub from '$lib/components/github.svelte';
</script>

<div class="navbar">
	<nav>
		<a href="/">Home</a>
		<a
			href="https://drive.google.com/file/d/1Oc2tLSkskX7b2g4yVCUOYE4DxeoSET-t/view?usp=sharing"
			target="_blank">Resume</a
		>
		<a href="https://www.linkedin.com/in/lillianmho/" target="_blank"><LinkedIn fill="#EDF1D6" /></a
		>
		<a href="https://github.com/lillianho5" target="_blank"><GitHub fill="#EDF1D6" /></a>
	</nav>
</div>

<style>
	nav {
		display: flex;
		justify-content: end;
		align-items: center;
	}

	.navbar {
		background-color: #609966;
		width: 100%;
		padding: 1rem;
	}

	a {
		margin: 0rem 2rem;
		color: #edf1d6;
		text-decoration: none;
	}

	a:hover {
		font-weight: bold;
	}
</style>
