<script>
	import Navbar from './navbar.svelte';
	import Qrcode from '../../assets/icons/qrcode.svelte';
	import LockIcon from '../../assets/icons/lock.svg';
	import CopyIcon from '../../assets/icons/copy.svg';
	import DownloadIcon from '../../assets/icons/download.svg';
	import CheckMarkIcon from '../../assets/icons/tickcircle.svg';

	import { slide } from 'svelte/transition';
	import { quintOut } from 'svelte/easing';
	import * as eases from 'svelte/easing';

	let showing = true;
	let currentEasing = eases.elasticOut;
	let duration = 1000;

	let isCopyShowing = true;

	let url = 'https://fli.ck/shortURL';
</script>

<article>
	<!-- Navbar -->
	<Navbar />

	<!-- Content -->
	<div class="content">
		<div class="box">
			<svelte:component this={Qrcode} />

			<div class="boxtext">
				<h4 class="title">Here’s your short URL!</h4>
				<h6 class="subheading">Share this shortened URL and spread your website to the world!</h6>
			</div>

			<div class="input">
				<div class="left">
					<LockIcon class="icon" />
					<span>{url}</span>
				</div>

				{#if isCopyShowing}
					<button
						on:click={() => {
							navigator.clipboard.writeText(url);
							isCopyShowing = false;

							setTimeout(() => {
								isCopyShowing = true;
							}, 3000);
						}}
					>
						<!-- Ignore the svelte warning in the below line -->
						<CopyIcon class="icon" />
					</button>
				{:else}
					<span transition:slide={{ delay: 250, duration: 300, easing: quintOut }}>
						<CheckMarkIcon class="icon" />
					</span>
				{/if}
			</div>

			<button class="download">
				<DownloadIcon class="icon" />
				<span>Download</span>
			</button>
		</div>
	</div>
</article>

<style>
	article {
		display: flex;
		align-items: stretch;
		justify-content: center;
		flex-direction: column;
		gap: 0;
		height: 100%;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 21px 23px;
		height: 100%;
		gap: 28px;
	}

	.box {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 21px 23px;
		gap: 28px;
		margin-top: -35px;
		max-width: 451px;
		width: 100%;

		background: #ffffff;
		box-shadow: 0px 47px 45px -18px rgba(54, 75, 106, 0.15);
		border-radius: 20px;
	}

	.input {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
		padding: 14px 20px;
		gap: 11px;
		width: 100%;
		background-color: #e5e9ed;
		border-radius: 8px;
	}

	.input {
		flex-shrink: 0;
	}

	.left {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: flex-end;

		padding: 0px;
		gap: 11px;
		font-weight: 500;
		font-size: 18px;
		line-height: 18px;
		overflow: hidden;

		color: #6a6a6a;
	}

	.left span {
		text-overflow: ellipsis;
		overflow: hidden;
	}

	.download {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		padding: 14px 73px;
		gap: 11px;

		width: 100%;

		background: #024df2;
		border-radius: 8px;
		font-weight: 500;
		font-size: 18px;

		border: none;
		cursor: pointer;
		transition: 0.3s filter ease-in-out;

		color: #ffffff;
	}

	.download:hover {
		filter: brightness(110%);
	}

	.download span {
		margin-bottom: -5px;
	}

	.boxtext {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 0px;
		gap: 9px;

		max-width: 200px;
		width: 100%;
	}

	.boxtext .title {
		font-weight: 600;
		font-size: 16px;
		line-height: 16px;

		text-align: center;

		color: #4c6177;
	}

	.boxtext .subheading {
		font-weight: 500;
		font-size: 14px;
		line-height: 14px;
		text-align: center;

		color: #99a1be;
	}
</style>


