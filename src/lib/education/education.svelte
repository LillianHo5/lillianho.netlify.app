<script>
	import Saos from 'saos';
	import Box from '$lib/components/box.svelte';

	const education = [
		{
			category: 'Education',
			data: [
				{
					position: 'University of California, San Diego',
					timeInPosition: 'September 2021 - December 2024',
					company: 'B.S. Computer Science, Minor in Cognitive Science',
					descriptionTitle: 'Activities and societies',
					description:
						'Women in Computing @ UCSD, Society of Women Engineers, Early Research Scholars Program, Triton NeuroTech, Triton Software Engineering'
				}
			]
		}
	];
</script>

{#each education as ed}
	<Saos
		animation="fade-in 1s cubic-bezier(0.390, 0.575, 0.565, 1.000) both"
		top={250}
		bottom={250}
		once={true}
	>
		<div id="education">
			<h2>{ed.category}</h2>
			<div class="education-container">
				{#each ed.data as item}
					<Box
						position={item.position}
						time={item.timeInPosition}
						company={item.company}
						skills={null}
						descriptionTitle={item.descriptionTitle}
						description={item.description}
						image={null}
						imageAlt={null}
						links={null}
						width="90%"
					/>
				{/each}
			</div>
		</div>
	</Saos>
{/each}

<style>
	#education {
		padding: 2em;
	}

	.education-container {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	h2 {
		text-align: center;
	}
</style>
