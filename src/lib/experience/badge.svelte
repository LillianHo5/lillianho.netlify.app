<script>
	export let description;
</script>

<div class="badge">
	<p>{description}</p>
</div>

<style>
	.badge {
		background-color: #eeedeb;
		border-radius: 10%;
		width: max-content;
		margin-right: 0.5rem;
		margin-top: 0.5rem;
		padding: 0 0.5rem;
	}
	p {
		line-height: 0;
		font-size: 16px;
		color: #686d76;
	}

	@media only screen and (max-width: 1000px) {
		p {
			font-size: 12px;
		}
	}
</style>
