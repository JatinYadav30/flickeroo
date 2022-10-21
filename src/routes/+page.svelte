<script>
	import Logo from '../assets/icons/logoLarge.svelte';
	import ShortenIcon from '../assets/icons/shortenIcon.svelte';
</script>

<article>
	<svelte:component this={Logo} />
	<div class="inputs">
		<input type="url" class="inputbox" placeholder="Input your long URL" />
		<button><svelte:component this={ShortenIcon} /><span>Shorten</span></button>
	</div>
</article>

<style>
	article {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 70px;
		height: 100%;
	}

	.inputs {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 0px;
		gap: 38px;
		width: 100%;
	}

	.inputbox {
		background: #ffffff;
		box-shadow: 0px 47px 45px -18px rgba(54, 75, 106, 0.15);
		border-radius: 10px;
		border: none;
		padding: 0;
		padding: 18px 31px;
		width: 80%;
		max-width: 700px;
	}

	button {
		background: #024df2;
		border-radius: 8px;
		padding: 14px 73px;
		gap: 11px;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		border: none;
		font-weight: 500;
		font-size: 18px;
		line-height: 14px;
		color: white;
	}

	button:hover {
		cursor: pointer;
	}

	.inputbox::placeholder {
		color: rgba(0, 0, 0, 0.2);
	}

	.inputbox:focus {
		outline: none;
	}

	button span {
		margin-bottom: -5px;
	}
</style>
