<svelte:head>
	<title>Mohit</title>
</svelte:head>

<main><slot /></main>

<style>
	:global(body, html) {
		background-color: #e9edf0;
		max-height: 100vh;
		font-family: 'Josefin Sans', sans-serif;
		height: 100%;
	}

	main {
		height: 100%;
		font-family: 'Josefin Sans', sans-serif;
	}

	:global(*) {
		box-sizing: border-box;
		margin: 0;
	}

	:global(.icon) {
		flex-shrink: 0;
	}

	:global(button, input) {
		font: inherit;
		background-color: inherit;
		border: none;
	}
</style>
