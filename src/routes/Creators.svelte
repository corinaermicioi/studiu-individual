<script>
	import { creators } from '../data';
</script>

<ul class="profiles">
	{#each creators as { src, name }}
		<li>
			<img {src} alt={`${name}'s avatar`} />
			<h4>{name}</h4>
		</li>
	{/each}
</ul>

<style>
	.profiles {
		list-style: none;
		overflow-x: scroll;
		display: flex;
		width: 100%;
		text-align: center;
	}
	.profiles > li {
		display: grid;
		margin-left: 20px;
		place-items: center;
		gap: 12px;
		padding: 20px 30px;
		border-radius: 30px;
		background-color: rgba(255, 255, 255, 0.1);
	}
	.profiles > li > img {
		width: 70px;
		height: 70px;
	}
	.profiles > li > h4 {
		font-size: 12px;
		margin: 0 -10px;
	}
	.profiles > li:last-child {
		margin-right: 18px;
	}
	.profiles::-webkit-scrollbar {
		display: none;
	}

	@media (min-width: 1024px) {
		.profiles > li > img {
			width: 120px;
			height: 120px;
		}
		.profiles > li > h4 {
			font-size: 18px;
		}
	}

	@media (min-width: 2400px) {
		.profiles {
			justify-content: center;
		}
	}
</style>
