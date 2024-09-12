<script>
	import Badge from './badge.svelte';
	export let position;
	export let company;
	export let time;
	export let skills;
	export let description;
	export let image;
	export let imageAlt;
</script>

<div class="box">
	<div class="gen-info">
		<div>
			<h2>{position}</h2>
			<p><strong>{company}</strong></p>
			<p>{time}</p>
		</div>
		{#if image && imageAlt}
			<img src={image} alt={imageAlt} />
		{/if}
	</div>
	<div class="skills-container">
		{#each skills as skill}
			<Badge description={skill} />
		{/each}
	</div>
	{#if description}
		<p>{description}</p>
	{/if}
</div>

<style>
	.box {
		padding: 1rem;
		border-radius: 8px;
		margin: 1rem;
		background-color: #f9f9f9;
		box-shadow: 10px 15px #609966;
		width: 40%;
	}
	.skills-container {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
	}
	.gen-info {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
	}
	h2 {
		margin: 0;
		font-size: 1.25rem;
	}
	p {
		margin: 0.5rem 0;
	}
	img {
		width: 5em;
		height: 5em;
		border-radius: 10px;
	}

	@media only screen and (max-width: 1000px) {
		.box {
			width: 80%;
		}

		h2 {
			font-size: 20px;
		}

		p {
			font-size: 16px;
		}
	}
</style>
