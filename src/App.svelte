<script>
  export let model;

  // Creates a Svelte store (https://svelte.dev/tutorial/writable-stores) that syncs with the named Traitlet example.py.
  import { createValue } from './stores';
  // createValue(model, /*Traitlet name*/, /*default value*/)

  let value = createValue(model, 'value', 0);
  let unit = createValue(model, 'unit', 'clicks');
  let numberList = createValue(model, 'numberList', []);

</script>

<style>
  h1 {
    color: pink;
  }
</style>

<h1>Welcome To The Widget:</h1>
<p>Here is an int: {$value} and here is a unicode string: {$unit}</p>
<button on:click={() => value.update((d) => d + 1)}>Increase Int</button>
<br />
<input bind:value={$unit}/>
<p>Displaying a DataFrame(Translated to 2D Array):</p>
{#each $numberList as subList}
<p>{#each subList as item} [{item}] {/each}</p>
{/each}