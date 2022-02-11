<script context="module">
	export const prerender = true;
</script>

<script>
	import CatFacts from '$lib/CatFacts.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<svelte:component this={CatFacts}></svelte:component>
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
