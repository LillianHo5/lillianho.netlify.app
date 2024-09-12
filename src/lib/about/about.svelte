<script>
	import headshot from '$lib/about/images/cropped_headshot.jpg';
</script>

<div class="about">
	<h1>Lillian Ho</h1>
	<div class="about-contents">
		<img class="img" src={headshot} alt="Lillian Ho Headshot" />
		<p>
			I'm an incoming 4th year at UC San Diego majoring in computer science and cognitive science. I
			enjoy building impactful software and am always looking to exploring new technologies. In my
			free time, I enjoy collecting Smiskis, knitting, and going on long walks.
			<br />
			<br /> I'm actively looking for new grad software engineering roles and off-season internships.
			Feel free to reach out via email or LinkedIn!
		</p>
	</div>
</div>

<style>
	.about {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		padding: 0 20em;
	}

	.about-contents {
		display: flex;
		flex-direction: row;
	}

	img {
		object-fit: cover;
		width: 500px;
		height: 400px;
		border-radius: 100%;
		padding-right: 5em;
	}
</style>
