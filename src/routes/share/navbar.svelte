<script>
	import LogoSmall from '../../assets/icons/logoSmall.svelte';
</script>

<nav>
	<svelte:component this={LogoSmall} />
</nav>

<style>
	nav {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		padding: 27px 53px;
		gap: 10px;
		width: 100%;
	}
</style>
