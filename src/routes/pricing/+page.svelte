<script>
	import PricingCards from './Pricings.svelte';
</script>

<svelte:head>
	<title>Pricing</title>
</svelte:head>

<main>
	<section>
		<h1>Choose the PERFECT plan for YOU</h1>
		<h4>Upgrades are as simple as installing new plugins</h4>
		<PricingCards />
	</section>
</main>

<style>
	h4 {
		text-align: center;
		font-size: 20px;
	}
	section {
		padding: 0 10vw;
	}
</style>
