<script>
	import Badge from '../experience/badge.svelte';
	export let position;
	export let company;
	export let time;
	export let skills;
	export let description;
	export let image;
	export let imageAlt;
	export let width = '40%';
</script>

<div class="box" style="width: {width};">
	<div class="gen-info">
		<div>
			{#if position}
				<h2>{position}</h2>
			{/if}
			{#if company}
				<p><strong>{company}</strong></p>
			{/if}
			{#if time}
				<p>{time}</p>
			{/if}
		</div>
		{#if image && imageAlt}
			<img src={image} alt={imageAlt} />
		{/if}
	</div>
	<div class="skills-container">
		{#if skills}
			{#each skills as skill}
				<Badge description={skill} />
			{/each}
		{/if}
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
