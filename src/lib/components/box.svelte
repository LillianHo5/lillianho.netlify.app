<script>
	import Badge from '$lib/experience/badge.svelte';

	export let position;
	export let company;
	export let time;
	export let skills;
	export let descriptionTitle;
	export let description;
	export let image;
	export let imageAlt;
	export let width = '40%';
	export let links;
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
	{#if descriptionTitle}
		<p><strong>{descriptionTitle}</strong>: </p>
	{/if}
	{#if description}
		{#if Array.isArray(description) && description.length > 1}
			<ul class="description">
				{#each description as desc}
					<li>{desc}</li>
				{/each}
			</ul>
		{:else}
			<p class="description">{description}</p>
		{/if}
	{/if}
	{#if links && links.length > 0}
		<p><strong>Links:</strong></p>
		<div class="links">
			<ul>
				{#each links as { label, url }}
					<li>
						<a href={url} target="_blank" rel="noopener noreferrer">{label}</a>
					</li>
				{/each}
			</ul>
		</div>
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
	p,
	ul {
		margin: 0.5rem 0;
	}
	img {
		width: 5em;
		height: 5em;
		border-radius: 10px;
	}
	.links a {
		margin-right: 0.5rem;
		color: #609966;
		text-decoration: none;
	}
	.links a:hover {
		text-decoration: underline;
		color: #99a555;
	}
	ul.description {
		padding-left: 1em;
		color: #609966;
	}
  ul.description li {
		margin-bottom: 0.5rem;
		font-size: 18px;
  }
  .links ul li::marker {
      color: #609966;
  }
	@media only screen and (max-width: 1000px) {
		.box {
			width: 80%;
		}

		h2 {
			font-size: 20px;
		}

		p,
		ul.description li {
			font-size: 16px;
		}
	}
</style>
