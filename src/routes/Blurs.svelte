<div class="blurs">
	<div>
		<img src="pink-blur.svg" alt="blur" />
		<img src="blue-blur.svg" alt="blur" />
	</div>
	<div>
		<img src="pink-blur.svg" alt="blur" />
		<img src="blue-blur.svg" alt="blur" />
	</div>
</div>

<style>
	.blurs > div {
		display: flex;
		rotate: -90deg;
		filter: blur(100px);
		-webkit-filter: blur(100px);
	}

	.blurs > div > img:nth-child(2) {
		rotate: 180deg;
	}

	.blurs {
		position: absolute;
		display: flex;
		justify-content: space-around;
		width: 100vw;
		overflow: hidden;
		z-index: -1;
		opacity: 70%;
		padding-bottom: 20vh;
	}

	.blurs > div:nth-child(1) {
		margin-right: -1000px;
	}

	.blurs > div:nth-child(2) {
		margin-left: -1000px;
	}

	@media (min-width: 1024px) {
		.blurs > div {
			margin: 0 !important;
		}
	}
</style>
