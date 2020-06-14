<script>
  export let rating = 0 
  if (typeof rating != 'number') rating = parseInt(rating)
  let rest = 5 - rating
  // let icon
  let error = false
  let icons = []
  let emptyIcons = []
  $: {
    icons.length = rating
    emptyIcons.length = rest

  }
  // $: {
  //   if(rating < 0 || rating > 5 ) error = true
  //   else 
    
  // }
  // $: icons = [...icons, ]
</script>
<div class=""
>


{#if error}
  
<!-- {:else} -->

  
<!-- {/if} -->
{:else if rating == 5}
   <!-- content here -->
  <i class=" star fas fa-star fa-5x"></i>

{:else if rating == 0}
  <i class="star nearly-hidden far fa-star fa-5x"></i>
   <!-- else content here -->
{:else}
  <div class="mp-quarter">
  {#each icons as icon, i}
    <!-- content here -->
    <i class="star fas fa-star"></i>
  {/each}
  {#each emptyIcons as icon, i}
    <!-- content here -->
    <i class="star far fa-star"></i>
  {/each}
  </div>
    
{/if}
</div>

  

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


