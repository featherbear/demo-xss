<script>
  export let query = null;

 function execScript(elem) {
  [...elem.querySelectorAll('script')].forEach(elem => {
    eval(elem.innerText)
  })
 }
</script>

{#if query}
  <div use:execScript>
    {@html "No results found for " + decodeURIComponent(query) + ". Try again!"}
  </div>
{:else}
  <div class="error">Enter something to search for...</div>
{/if}
