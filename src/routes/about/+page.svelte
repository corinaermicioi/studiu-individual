<script>
	const images = Array.from({ length: 12 }, (_, i) => `image-${i + 1}`);
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<main>
	<section>
		<h1>ABOUT</h1>
		<iframe
			src="https://www.youtube.com/embed/rNSIwjmynYQ?si=eYU3Pnv1gZce9j4M"
			title="YouTube video player"
			frameborder="0"
			allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
			allowfullscreen
		></iframe>
		<p>
			Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut
			labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
			laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
			voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
			non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
		</p>
	</section>
	<section>
		<h1>MEET OUR FOUNDERS</h1>
		<img src="founders.jpg" alt="founders" class="founders" usemap="#image-map" />
		<map name="image-map">
			<area
				target="_blank"
				alt="Geraldine Abbey"
				title="Geraldine Abbey"
				href="https://www.prospects.ac.uk/case-studies/software-engineer-geraldine-abbey"
				coords="154,425,151,401,139,398,138,383,163,313,169,287,142,220,151,164,172,156,178,106,199,52,233,39,265,52,279,80,283,114,285,138,321,175,312,178,355,253,324,284,306,281,298,295,298,398,287,424"
				shape="poly"
			/>
			<area
				target="_blank"
				alt="Vivian Knight"
				title="Vivian Knight"
				href="https://www.prospects.ac.uk/case-studies/tech-plus-analyst-vivian-knight"
				coords="351,427,345,390,332,382,353,303,328,284,355,266,354,244,346,229,369,168,392,158,399,76,426,41,457,48,470,67,492,164,502,174,493,210,468,279,496,398,447,409,444,426"
				shape="poly"
			/>
		</map>
	</section>
	<section>
		<h1>EVENTS</h1>
		<div class="clearfix">
			{#each images as image}
				<div class="img-container">
					<img src={image + '.jpg'} alt={image} />
				</div>
			{/each}
		</div>
	</section>
	<section>
		<h1>DOWNLOADS</h1>
		<div class="downloads">
			<a class="primary" href="powerpoint.pptx" target="_blank">Presentation</a>
			<a class="primary" href="workplace.pdf" target="_blank">Communication ways</a>
			<a class="primary" href="best-workplace.pdf" target="_blank">General rules</a>
		</div>
	</section>
</main>

<style>
	iframe {
		height: 112%;
	}

	img:not(.founders) {
		height: 100%;
		width: 100%;
	}

	.founders {
		max-width: 90vw;
	}

	.img-container {
		float: left;
		width: 50%;
		padding: 5px;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.clearfix,
	p,
	iframe {
		padding: 0 10vw;
	}

	.downloads {
		width: 100%;
		padding: 0 16vw;
		display: flex;
		justify-content: space-around;
		flex-direction: column;
	}

	.downloads > a {
		text-decoration: none;
		text-align: center;
	}

	img {
		transition-duration: 0.3s;
	}

	.img-container:hover ~ .img-container > img {
		filter: brightness(30%);
	}

	@media (min-width: 768px) {
		.img-container {
			width: 33.3%;
		}
	}

	@media (min-width: 1280px) {
		.clearfix,
		p,
		iframe {
			padding: 0 15vw;
		}

		iframe {
			width: 100%;
			height: 540px;
		}

		.img-container {
			width: 25%;
		}

		.downloads {
			flex-direction: row;
			padding-top: 20px;
		}
	}
</style>
