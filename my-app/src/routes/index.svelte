<script context="module">
	export const prerender = true;
</script>

<script>
	import AppleApps from '$lib/AppleApps.svelte'
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<svelte:component this={AppleApps}></svelte:component>
</section>

<style>
	/* section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	} */
</style>
