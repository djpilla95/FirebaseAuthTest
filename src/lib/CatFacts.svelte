<script>
    import { onMount } from 'svelte';

	let catFacts = new Map();

	onMount(async () => {
		let res = await fetch(`https://cat-fact.herokuapp.com/facts`);
		let data = await res.json();
        const newFacts = new Map();
		data.forEach((element) => {
			newFacts.set(element._id, {
				description: element.text,
				checked: false
			});
		});
        catFacts = newFacts;
        console.log('catFacts', catFacts);
	});
</script>

{#each [...catFacts] as [key, value]}
	<h3>{value.description}</h3>
    <input type="checkbox" value="{key}" bind:checked={value.checked}>
    <label for="{key}">Is this true?</label><br>
	{#if value.checked}
        <span>This value is {value.checked}</span>
    {/if}
{/each}
