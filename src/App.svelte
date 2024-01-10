<script>
	let name = 'world'
	let toggle = false
	let fruitName = 'Fruits'
	let fruits = ['Apple', 'Banana', 'Cherry', 'Orange', 'Mange']
	
	let age = 85
	function assign() {
		name = 'soonhan'
		age = 36
	}
	function deleteFruit() {
		fruits = fruits.slice(1);
	}
</script>

<button on:click={() => {toggle = !toggle}}>
	Toggle
</button>

<h1>Hello {fruitName}!</h1>
<ul>
	{#each fruits as fruit}
		<li>{fruit}</li>
	{/each}
</ul>

<button on:click={deleteFruit}>
	Eat it!
</button>

{#if toggle}
	<h1>Hello {name}!</h1>
{:else}
	<div>No name!</div>
{/if}

<h2 class={age < 85 ? 'active' : ''}>
	{age}
</h2>
<img src="" alt={name} />
<input type="text" bind:value={name} />
<button on:click={assign}>
	Assign
</button>

<style>
	h1 {
		color: red;
	}
	.active {
		color: blue;
	}
</style>