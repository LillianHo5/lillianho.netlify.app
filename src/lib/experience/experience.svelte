<script>
	import Saos from 'saos';

	import Box from '$lib/components/box.svelte';
	import LinkedInLogo from '$lib/experience/images/linkedin.png';
	import LibertyLogo from '$lib/experience/images/liberty_mutual.webp';
	import LockPodLogo from '$lib/experience/images/lockpod.jpeg';
	import TSELogo from '$lib/experience/images/tse.png';

	const experiences = [
		{
			category: 'Work Experience',
			data: [
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'June 2024 - September 2024',
					company: 'LinkedIn',
					skills: ['Java', 'Software Design', 'Distributed Systems', 'JUnit', 'Mockito', 'Docker'],
					description:
						'Developed erasure coding for LinkedIn’s storage, reducing overhead by 75% and authored a design document to guide implementation.',
					image: LinkedInLogo,
					imageAlt: 'LinkedIn Logo'
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'June 2023 - September 2023',
					company: 'Liberty Mutual Insurance',
					skills: ['SQL', 'Python', 'React.js', 'TypeScript', 'DBVisualizer', 'AWS'],
					description:
						' Improved data integrity and user access by modifying reinsurance claims databases and optimizing UI readability with React.',
					image: LibertyLogo,
					imageAlt: 'Liberty Mutual Insurance Logo'
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'April 2023 - June 2023',
					company: 'LockPod',
					skills: ['React Native', 'TypeScript', 'Figma'],
					description:
						'Implemented and designed user interfaces for the LockPod app using TypeScript and Figma.',
					image: LockPodLogo,
					imageAlt: 'Liberty Mutual Insurance Logo'
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'April 2022 - October 2022',
					company: 'Skinalytics',
					skills: ['Java', 'Android Development'],
					description:
						'Resolved UI bugs in the Skinalytics Android app and refactored code into a modular architecture to enhance maintainability and user experience.'
				}
			]
		},
		{
			category: 'Extracurricular Experience',
			data: [
				{
					position: 'Software Developer',
					timeInPosition: 'November 2022 - Present',
					company: 'Triton Software Engineering',
					skills: [
						'HTML/CSS',
						'Svelte',
						'TypeScript',
						'React Native',
						'Next.js',
						'Tailwind CSS',
						'MongoDB'
					],
					description:
						'Developed an interactive landing page and a mobile/web portal, improving user engagement and accessibility for FixNation and UCSD’s Division of Sports Medicine.',
					image: TSELogo,
					imageAlt: 'Triton Software Engineering Logo'
				},
				{
					position: 'Undergraduate Researcher',
					timeInPosition: 'September 2022 - September 2023',
					company: 'UC San Diego (Early Research Scholars Program)',
					skills: ['Kotlin', 'Android Development'],
					description:
						'Developed an Android app using the BirdNet TFLite Model in Kotlin to repurpose old smartphones as carbon-efficient sensors for classifying birds from recorded audio samples.'
				}
			]
		}
	];
</script>

{#each experiences as exp}
	<Saos
		animation={'fade-in 1s cubic-bezier(0.390, 0.575, 0.565, 1.000) both'}
		top={250}
		bottom={250}
		once={true}
	>
		<div id="experience">
			<h2>{exp.category}</h2>
			<div class="experience-container">
				{#each exp.data as item}
					<Box
						position={item.position}
						time={item.timeInPosition}
						company={item.company}
						skills={item.skills}
						description={item.description}
						image={item.image}
						imageAlt={item.imageAlt}
						width={'40%'}
					/>
				{/each}
			</div>
		</div>
	</Saos>
{/each}

<style>
	#experience {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 2em;
	}

	.experience-container {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: space-around;
	}

	h2 {
		text-align: center;
	}
</style>
