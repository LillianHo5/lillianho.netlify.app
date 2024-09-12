<script>
	import Box from '$lib/experience/box.svelte';
	const experiences = [
		{
			position: 'Software Engineer Intern',
			timeInPosition: 'June 2024 - September 2024',
			company: 'LinkedIn',
			description: 'Worked on storage infrastructure and developed erasure coding system.'
		},
		{
			position: 'Software Engineer Intern',
			timeInPosition: 'January 2023 - May 2023',
			company: 'Liberty Mutual Insurance',
			description: 'Developed frontend components using React.js and optimized UI performance.'
		}
	];
</script>

<div class="experience">
	<h2>Work Experience</h2>
	<div class="experience-container">
		{#each experiences as exp}
			<Box
				position={exp.position}
				time={exp.timeInPosition}
				company={exp.company}
				description={exp.description}
			/>
		{/each}
	</div>
</div>

<style>
	.experience {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
</style>
