<script>
  export let rating = 0 
  export let icon = ''
  if (typeof rating != 'number') rating = parseInt(rating)
  let error = false
  let modes = []

  $: {
    modes.length = rating
    modes.length = 5
    modes.fill('far')
    modes.fill('fas', 0, rating)
    console.log(icon)
  }
  
</script>

{#if rating == 5}
  <i class="{icon} fas fa-{icon} fa-fw fa-5x"></i>

{:else if rating == 0}
  <i class="{icon} nearly-hidden far fa-{icon} fa-fw fa-5x"></i>
{:else}
  <div class="mp-quarter">
  {#each modes as mode, i}
    <i class="{icon} {mode} fa-{icon} fa-fw fa-2x"></i>
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

  .heart {
    color: red;
  }
  .thumbs-up {
    color: deepskyblue;
  }
  i {
    /* padding: 0.25rem; */
  }
  .smile-beam {
    color: gold;
  }
</style>


