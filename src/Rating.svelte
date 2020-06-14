<script>
  export let rating = 0 
  if (typeof rating != 'number') rating = parseInt(rating)
  let error = false
  let icons = []

  $: {
    icons.length = rating
    icons.length = 5
    icons.fill('far')
    icons.fill('fas', 0, rating)
  }
  
</script>

{#if rating == 5}
  <i class=" star fas fa-star fa-5x"></i>

{:else if rating == 0}
  <i class="star nearly-hidden far fa-star fa-5x"></i>
{:else}
  <div class="mp-quarter">
  {#each icons as icon, i}
    <i class="star {icon} fa-star"></i>
  {/each}

  </div>
    
{/if}

  

<style>
  .error {
    color: orangered;
  }
  .success {
    color: yellowgreen;
  }
  .star {
    color: goldenrod;
  }
  .nearly-hidden {
    opacity: 0.25;
  }
  .mp-quarter {
    display: inline ;
    padding: 0 0.25rem;
    margin: 0 .25rem;

  }
</style>


