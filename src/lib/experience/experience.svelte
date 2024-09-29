<script>
	import { onMount } from 'svelte';
	import Saos from 'saos';

	import Box from '$lib/components/box.svelte';
	import LinkedInLogo from '$lib/experience/images/linkedin.png';
	import LibertyLogo from '$lib/experience/images/liberty_mutual.webp';
	import LockPodLogo from '$lib/experience/images/lockpod.jpeg';
	import TSELogo from '$lib/experience/images/tse.png';
	import TNTLogo from '$lib/experience/images/tnt_logo.svg';
	import CAIDALogo from '$lib/experience/images/CAIDA.png';

	const experiences = [
		{
			category: 'Work Experience',
			data: [
				{
					position: 'Frontend Developer REU (Research Experience for Undergraduates)',
					timeInPosition: 'September 2024 - Present',
					company: 'Center for Applied Internet Data Analysis',
					skills: ['React.js', 'JavaScript', 'GitLab'],
					description:
						'Collaborating with UX designers and researchers to develop responsive web interfaces for CAIDA’s platform.',
					image: CAIDALogo,
					imageAlt: 'CAIDA Logo',
					links: []
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'June 2024 - September 2024',
					company: 'LinkedIn',
					skills: ['Java', 'Software Design', 'Distributed Systems', 'JUnit', 'Mockito', 'Docker'],
					description:
						'Implemented erasure coding for LinkedIn’s next-gen storage system, reducing storage overhead by 75% compared to traditional replication methods while ensuring data durability.',
					image: LinkedInLogo,
					imageAlt: 'LinkedIn Logo',
					links: []
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'June 2023 - September 2023',
					company: 'Liberty Mutual Insurance',
					skills: ['SQL', 'Python', 'React.js', 'TypeScript', 'DBVisualizer', 'AWS'],
					description:
						'Updated a reinsurance claims database by modifying 30% of the data, improving integrity and accessibility using SQL, AWS Glue, and Power BI. Improved data readability on the reinsurance application portal by updating currency formats with HTML, CSS, TypeScript, and React.',
					image: LibertyLogo,
					imageAlt: 'Liberty Mutual Insurance Logo'
				},
				{
					position: 'Software Engineer Intern',
					timeInPosition: 'April 2023 - June 2023',
					company: 'LockPod',
					skills: ['React Native', 'TypeScript', 'Figma'],
					description:
						'Implemented and designed user interfaces for the LockPod mobile app using TypeScript and Figma.',
					image: LockPodLogo,
					imageAlt: 'LockPod Insurance Logo'
					// links: [{ label: 'LockPod Website', url: 'https://www.lockpod.us/' }]
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
						'Collaborated with 13 students to create an <a href="https://landing.fixnation.org/" target="_blank" rel="noopener noreferrer">interactive landing page</a> for FixNation, attracting 1,200+ visitors, and contributed to building a real-time medical assistance <a href="https://github.com/TritonSE/DFM-Sideline-Sidekick-App" target="_blank" rel="noopener noreferrer">portal and mobile application</a> for UCSD’s Division of Sports Medicine using MongoDB, React Native, and TypeScript.',
					image: TSELogo,
					imageAlt: 'Triton Software Engineering Logo'
					// links: [
					// 	{ label: 'FixNation Landing Page', url: 'https://landing.fixnation.org/' },
					// 	{
					// 		label: 'FixNation Landing Page GitHub Repo',
					// 		url: 'https://github.com/TritonSE/FIX-Landing-Page'
					// 	},
					// 	{
					// 		label: 'DFM Sideline Sidekick GitHub Repo',
					// 		url: 'https://github.com/TritonSE/DFM-Sideline-Sidekick-App'
					// 	}
					// ]
				},
				{
					position: 'Webmaster',
					timeInPosition: 'September 2023 - June 2024',
					company: 'Triton NeuroTech',
					skills: ['React.js', 'JavaScript', 'Figma'],
					description:
						'Managed and maintained <a href="https://neurotechx.ucsd.edu/" target="_blank" rel="noopener noreferrer">Triton NeuroTech’s website</a> using React.js, regularly updating content for events and ongoing projects, and revamped the site with a responsive design.',
					// links: [{ label: 'Triton NeuroTech Website', url: 'https://neurotechx.ucsd.edu/' }]
					image: TNTLogo,
					imageAlt: 'Triton NeuroTech Logo'
				},
				{
					position: 'Undergraduate Researcher',
					timeInPosition: 'September 2022 - September 2023',
					company: 'UC San Diego (Early Research Scholars Program)',
					skills: ['Kotlin', 'Android Development'],
					description:
						'Developed an <a href="https://github.com/The-Renee-Project/AudioBird2" target="_blank" rel="noopener noreferrer">Android app</a> with 2 students using the BirdNet TFLite Model in Kotlin to repurpose old smartphones as carbon-efficient sensors for classifying birds from recorded audio samples.'
				}
			]
		}
	];

	let isMobile = false;

	const checkScreenWidth = () => {
		isMobile = window.innerWidth <= 1000;
	};

	onMount(() => {
		checkScreenWidth();
		window.addEventListener('resize', checkScreenWidth);
	});
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
						links={item.links}
						width={isMobile ? '80%' : '40%'}
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
