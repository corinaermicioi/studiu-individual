<script>
	import Blurs from './Blurs.svelte';
	import Footer from './Footer.svelte';
	import Navbar from './Navbar.svelte';
	import '../styles.css';
</script>

<Blurs />

<Navbar />

<slot />

<Footer />
