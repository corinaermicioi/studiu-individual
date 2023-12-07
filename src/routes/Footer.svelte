<script>
	import { links } from '../data';
</script>

<footer class="mobile">
	<form action="">
		<input type="email" name="email" value="Your e-mail" placeholder="Your e-mail" class="email" />
		<button class="subscribe" type="submit">Subscribe Now!</button>
	</form>
	<hr />

	<div class="container">
		<div class="links">
			{#each links as { href, name }}
				<a {href}>{name}</a>
			{/each}
		</div>
		<img src="main-logo.svg" alt="main logo" class="logo" />
		<div class="icons">
			<a href="https://twitter.com/" target="_blank"
				><img src="twitter.svg" alt="twitter" width="30" height="30" /></a
			>
			<a href="https://instagram.com/" target="_blank"
				><img src="instagram.svg" alt="instagram" width="30" height="30" /></a
			>
			<a href="https://youtube.com/" target="_blank"
				><img src="youtube.svg" alt="youtube" width="30" height="30" /></a
			>
		</div>
	</div>
	<hr />

	<p class="copyright">All rights reserved 2023</p>
</footer>

<footer class="desktop">
	<div class="left">
		<form action="">
			<input
				type="email"
				name="email"
				value="Your e-mail"
				placeholder="Your e-mail"
				class="email"
			/>
			<button class="subscribe" type="submit">Subscribe Now!</button>
		</form>
		<hr />
		<p class="copyright">All rights reserved 2023</p>
	</div>
	<img src="main-logo.svg" alt="main logo" class="logo" />
	<div>
		<div class="links">
			{#each links as { href, name }}
				<a {href}>{name}</a>
			{/each}
		</div>
		<hr />
		<div class="icons">
			<a href="https://twitter.com/" target="_blank"
				><img src="twitter.svg" alt="twitter" width="30" height="30" /></a
			>
			<a href="https://instagram.com/" target="_blank"
				><img src="instagram.svg" alt="instagram" width="30" height="30" /></a
			>
			<a href="https://youtube.com/" target="_blank"
				><img src="youtube.svg" alt="youtube" width="40" height="30" /></a
			>
		</div>
	</div>
</footer>

<style>
	footer {
		display: grid;
		padding: 20px;
		gap: 20px;
		text-align: center;
		background-color: #311a31;
		border-top: 1px solid rgba(255, 255, 255, 0.2);
	}

	.logo {
		width: 70px;
		height: 70px;
		position: absolute;
		left: 20px;
		right: 0;
		bottom: 0;
		top: 16px;
		margin: 0 auto;
		z-index: 0;
	}

	form {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	input,
	button {
		border: none;
		outline: none;
		font-size: 14px;
		padding: 10px 18px;
		border-radius: 13px;
		height: fit-content;
	}

	.email {
		background-color: rgba(255, 255, 255, 0.1);
	}

	.subscribe {
		background-color: var(--light-pink);
		margin-left: -30px;
		transition-duration: 0.3s;
		font-size: 10px;
	}

	.subscribe:hover {
		scale: 110%;
	}

	hr {
		border: none;
		margin: 0 -20px;
		border-top: 0.5px solid rgba(255, 255, 255, 0.2);
	}

	.container {
		position: relative;
		display: flex;
		justify-content: space-between;
		padding: 0 20px;
		align-items: center;
	}

	.links,
	.icons {
		display: grid;
		text-align: left;
	}

	.links > * {
		font-size: 14px;
		text-decoration: none;
	}

	.icons > a {
		transition-duration: 0.3s;
	}
	.icons > a:hover {
		scale: 110%;
	}

	.desktop {
		display: none;
	}

	@media (min-width: 360px) {
		.subscribe {
			font-size: 14px;
		}
	}

	/* @media (min-width: 1024px) { */
	@media (min-width: 1230px) {
		footer {
			padding: 20px 40px;
		}

		hr {
			margin: 0 -40px;
		}

		.mobile {
			display: none;
		}

		.desktop {
			display: flex;
			align-items: center;
		}

		.desktop > div {
			display: grid;
			gap: 20px;
			width: 100%;
		}

		.logo {
			width: 140px;
			height: 140px;
			position: static;
			margin: 0 85px 0 100px;
		}

		.icons,
		.links {
			display: flex;
			justify-content: end;
			gap: 30px;
			align-items: center;
		}

		.links > * {
			font-size: 24px;
		}

		.links > *:hover {
			text-decoration: underline;
			text-underline-offset: 4px;
		}

		.icons {
			gap: 10px;
		}

		.left > * {
			display: flex;
			justify-content: start;
			font-size: 24px;
		}

		.left > form > * {
			font-size: 20px;
			padding: 14px 24px;
		}
	}
</style>
