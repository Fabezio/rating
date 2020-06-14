<script>
  export let rating = 0 
  let icons = []
  // let icon
  let error = false
  $: {
    if(rating < 0 || rating > 5 ) error = true
    else icons.length = rating
    
  }
  // $: icons = [...icons, ]
</script>


{#if error}
  <div class="error">Entre une valeur de 0 à 5</div>
<!-- {:else} -->

  
{/if}
{#if rating == 5}
   <!-- content here -->
  <i class=" star fas fa-star fa-4x"></i>

{:else if rating == 0}
  <i class="star nearly-hidden far fa-star fa-5x"></i>
   <!-- else content here -->
{:else}
  {#each icons as icon, i}
    <!-- content here -->
    <i class="star fas fa-star"></i>
  {/each}
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
</style>


