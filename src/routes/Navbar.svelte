<script>
	import { page } from '$app/stores';
	import { links } from '../data';

	let mobileMenuOpened = false;

	function handleClick() {
		mobileMenuOpened = !mobileMenuOpened;
	}
</script>

<nav>
	<img src="main-logo.svg" alt="main logo" class="logo" />

	{#each links as { href, name }}
		<a {href} class:current={$page.url.pathname === href}>{name}</a>
	{/each}

	<input type="text" placeholder="🔍 Search" value="🔍 Search" class="search" />
	<img src="current-user.svg" alt="current user" width="40" height="40" class="avatar" />

	<div class="mobile-nav">
		{#if mobileMenuOpened}
			<div class="opened">
				{#each links as { href, name }}
					<a {href} class:current={$page.url.pathname === href} on:click={handleClick}>{name}</a>
				{/each}
				<button on:click={handleClick}>close</button>
			</div>
		{:else}
			<button on:click={handleClick} class="toggler"
				><img src="hamburger.svg" alt="hamburger menu" /></button
			>
		{/if}
	</div>
</nav>

<style>
	nav {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 20px;
		font-size: 24px;
	}
	nav > * {
		z-index: 10;
	}

	.logo {
		width: 50px;
		height: 50px;
	}

	input {
		all: unset;
		background-color: #ffffff1a;
		padding: 8px 10px;
		border-radius: 50px;
		font-size: 12px;
	}

	a {
		text-decoration: none;
		transition-duration: 0.3s;
		line-height: 1.2;
	}

	nav > a {
		display: none;
	}

	a:hover {
		text-shadow: 0 0 20px var(--light-pink);
		scale: 110%;
	}

	.current {
		border-bottom: 3px solid var(--light-pink);
	}

	.avatar {
		height: 30px;
		width: 30px;
	}

	.opened {
		position: absolute;
		top: 0;
		right: 0;
		background-color: rgba(0, 0, 0, 0.7);
		backdrop-filter: blur(8px);
		width: 100vw;
		height: 100vh;
		display: grid;
		place-items: center;
		padding: 28vh 0px;
	}

	.toggler {
		all: unset;
		display: flex;
		width: 26px;
		height: 26px;
		overflow: hidden;
	}

	button {
		all: unset;
		border: 3px solid var(--light-pink);
		padding: 10px 20px;
		border-radius: 50px;
		font-size: 16px;
		margin-top: 10vh;
	}

	@media (min-width: 1024px) {
		.logo {
			width: 100px;
			height: 100px;
		}

		nav {
			padding: 20px 30px;
		}

		nav > a {
			display: block;
		}

		input {
			padding: 10px 14px;
			font-size: 18px;
		}

		.avatar {
			width: 50px;
			height: 50px;
		}

		.mobile-nav {
			display: none;
		}
	}
</style>
