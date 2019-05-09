<svelte:head>
	<title>Simple TODO App with Svelte - Sapper</title>
</svelte:head>

<h2>TODO List</h2>

<ul>
  {#each data as name}
    <li>
      {name} <button on:click={() => deleteFruit(name)}>X</button>
    </li>
  {/each}
</ul>

<input bind:value={fruitName}/>
<button on:click={addFruit}>Add</button>

<script>
let data = [ 'apel', 'jeruk', 'pisang' ];
let fruitName = '';

const addFruit = () => {
  data.push(fruitName);
  data = data;
  fruitName = '';
};

const deleteFruit = (name) => {
  data = data.filter(fruitName => fruitName !== name);
}
</script>
