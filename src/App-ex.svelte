<script>
	import Fruits from "./Fruits.svelte";
	// import { onMount } from "svelte"
	let name = 'world'
	let toggle = false
	let fruitName = 'Fruits'
	let fruits = ['Apple', 'Banana', 'Cherry', 'Orange', 'Mange']
	let isRed = false
	let text = ''
	// onMount(() => {
	// 	const box = document.querySelector('.box')
	// 	box.addEventListener('click', () => {isRed = !isRed})
	// })
	
	let age = 85
	function assign() {
		name = 'soonhan'
		age = 36
	}
	function deleteFruit() {
		fruits = fruits.slice(1);
	}
	function enter() {
		name = 'enter'
	}
	function leave() {
		name = 'leave'
	}
</script>

<Fruits {fruits} />
<!-- <Fruits {fruits} reverse={true} /> -->
<Fruits {fruits} reverse />
<Fruits {fruits} slice="-2" />
<Fruits {fruits} slice="0, 3" />

<h1>
	{text}
</h1>
<input type="text"
		value={text}
		on:input={(e) => {text = e.target.value}} />
<input type="text"
		bind:value={text} />

<button on:click={() => {text = 'Soonhan'}}>
	Click!
</button>

<h1>Hello {name}!</h1>
<div class="box" 
	style="background-color: {isRed ? 'red' : 'orange'};"
	on:click={() => { isRed = !isRed }}
	on:mouseenter={enter}
	on:mouseleave={leave}>
	Box!
</div>

<button on:click={() => {toggle = !toggle}}>
	Toggle
</button>

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

	.box {
		width: 300px;
		height: 150px;
		background-color: orange;
	}
</style>