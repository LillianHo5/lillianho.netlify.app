<script>
	export let position;
	export let company;
	export let time;
	export let description;
</script>

<div class="box">
	<h2>{position}</h2>
	<p><strong>{company}</strong></p>
	<p>{time}</p>
	{#if description}
		<p>{description}</p>
	{/if}
</div>

<style>
	.box {
		border: 1px solid #ccc;
		padding: 1rem;
		border-radius: 8px;
		margin-bottom: 1rem;
		background-color: #f9f9f9;
	}
	h2 {
		margin: 0;
		font-size: 1.25rem;
	}
	p {
		margin: 0.5rem 0;
	}
</style>
