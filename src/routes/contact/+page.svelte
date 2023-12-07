<svelte:head>
	<title>Contact</title>
</svelte:head>

<main>
	<section>
		<h1>Let's get in touch</h1>
		<p>
			For all general inquires, please contact us directly via email at canius@gmail.com or use the
			form.
		</p>
	</section>
	<section>
		<h1>Contact us</h1>
		<form action="">
			<input type="text" placeholder="Name" required />
			<input type="email" placeholder="Email" required />
			<input type="text" placeholder="Subject" />
			<textarea placeholder="Message" cols="30" rows="10" required />
			<button class="primary" type="submit">Send</button>
		</form>
	</section>
</main>

<style>
	section {
		padding: 0 10vw;
	}

	form {
		display: grid;
		gap: 10px;
	}

	input,
	textarea {
		all: unset;
		border: 1px solid rgba(255, 255, 255, 0.7);
		padding: 15px 20px;
		width: calc(100% - 40px);
	}

	button {
		width: fit-content;
		margin: 0 auto 10px auto;
	}

	@media (min-width: 1024px) {
		main {
			display: flex;
			padding: 0 15vw;
		}
		h1 {
			text-align: left;
		}
		section {
			display: flex;
			flex-direction: column;
			justify-content: center;
			padding: 0;
		}
		section:first-child {
			max-width: 400px;
		}
		section:nth-child(2) {
			width: 100%;
		}
		form {
			width: 100%;
			gap: 15px;
			display: grid;
			place-items: center;
		}
		input,
		textarea {
			width: 30vw;
		}
	}
</style>
