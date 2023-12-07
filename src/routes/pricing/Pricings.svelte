<script>
	import { pricings } from '../../data';
</script>

<div class="container">
	{#each pricings as { price, name, description, list, badge }}
		<div class="card" class:purple={badge}>
			<div>
				<span class="badge" class:hidden={!badge}>{badge}</span>
				<h2 class="price">${price}<span>/month</span></h2>
				<h3 class="name">{name}</h3>
				<p class="description">{description}</p>
				<ul>
					{#each list as item}
						<li>{item}</li>
					{/each}
				</ul>
			</div>
			<button>Choose plan</button>
		</div>
	{/each}
</div>

<style>
	.container {
		display: grid;
		gap: 50px;
	}
	.card {
		border-radius: 20px;
		background-color: white;
		padding: 30px;
		width: 100%;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		position: relative;
		transition-duration: 0.5s;
	}
	.card:hover {
		transform: translateY(-20px);
	}
	.price,
	.name,
	.description,
	span,
	li {
		color: rgb(25, 29, 79);
	}
	.price {
		font-size: 30px;
		font-weight: 700;
	}
	.name {
		font-size: 22px;
		font-weight: 500;
	}
	.description {
		font-size: small;
	}
	span {
		font-size: 18px;
		font-weight: 400;
	}
	ul {
		margin: 14px 0;
	}
	li {
		margin: 0;
		padding-left: 22px;
		padding-top: 2px;
		list-style: none;
		/* $img is fix for production, check vite.config.ts for details */
		background-image: url('$img/check-circle.svg');
		background-repeat: no-repeat;
		background-position: left center;
		background-size: 16px;
	}
	button {
		color: white;
		background-color: rgb(145, 142, 167);
		font-weight: 700;
		border: none;
		padding: 14px 0;
		border-radius: 14px;
		width: 100%;
		font-size: 16px;
		margin-top: 20px;
		transition-duration: 0.3s;
	}
	button:hover {
		scale: 110%;
	}
	.hidden {
		display: none !important;
	}
	.badge {
		display: block;
		position: absolute;
		top: 16px;
		right: 16px;
		font-size: 8px;
		border-radius: 30px;
		padding: 8px 10px;
		font-weight: 700;
		background-color: rgba(134, 61, 167, 0.4);
	}

	.purple {
		background-color: #231d4f;
	}
	.purple * {
		color: white;
	}
	.purple button,
	.purple .badge {
		color: white;
		background-color: rgb(134, 61, 167);
	}

	@media (min-width: 1024px) {
		.container {
			grid-template-columns: repeat(3, minmax(0, 1fr));
			place-items: center;
		}
	}
</style>
