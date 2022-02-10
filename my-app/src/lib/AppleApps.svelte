<script>
    import { onMount } from 'svelte'

    let catFacts = []
    let checked;

    onMount(async () => {
		const res = await fetch(`https://cat-fact.herokuapp.com/facts`);
		catFacts = await res.json();
        catFacts.flat();
	});
</script>

{#each catFacts as fact}
    <h3>{fact.text}</h3>
    <input type="checkbox" value="{fact._id}" bind:checked={checked}>
    <label for="{fact._id}">Is this true?</label><br>
    {#if checked}
        <span>This value is {fact.status.verified}</span>
    {/if}
{/each}