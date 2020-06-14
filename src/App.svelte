<script>
	import Rating from './Rating.svelte'
	export let name
	let rating = 3
</script>

<main>
	<h1>{name}</h1>
	<input type="range" min="0" max="5" bind:value={rating}>
	<br>
	{#if rating > 5 || rating < 0}
	<div class="error">Oops... Something went wrong</div>
	{:else}
	<div class="">
		<div class="rating">
			<Rating class="" {rating} />
		</div>
	</div>
	{/if}
	<!-- <p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p> -->
</main>

<style>
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
	.error {
    color: orangered;
  }
	.thumbnail {
		border: 1px groove black;
		border-radius: 1rem;
		width: 7rem;
		height: 7rem;
		/* vertical-align: auto;		 */
		display: block;
		margin: auto;
		
	}

	.thumbnail .rating {
		margin: 0;
		padding: 0;
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>