<script>
	import { shuffle } from "lodash";
	export let name;
	const nm= 'deepshikha'
	const tagdata='<b>html rendering</b>'
	const headingId='attribute_binding'
	const disabled=true
	const status='danger'
	const correct=true
	const num=4
	let nameList=['deep','shikha','verma']
	const shuffleNames = () => {
		nameList = shuffle(nameList);
  };
</script>

<main>
	<!-- <h1 >Hello {name}!</h1>
	<h2 class={correct?status:'success'}>Welcome {nm} </h2>
	<h2>{@html tagdata}</h2>
	<h2 id={headingId}> attribute binding</h2>
	<button {disabled}> click </button>
	<h2 class:danger={correct}>custom directive </h2> -->
	{#if num === 0}
	<h2>num is zero</h2>
	{:else if num<0}
	<h2>num is negative</h2>
	{:else if num >0}
	<h2>num is positive </h2>
	{:else}
	<h2>not a num</h2>
	{/if}
	{#each nameList as name, index (name)}
	<h2>{index+1} {name}</h2>
	{/each}
	<button on:click={shuffleNames}>Shuffle!</button>

</main>

<style>
	.danger{
		color:blue;
	}
	.success{
		color:green;
	}
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>