<style>
  /* works locally
  BUT
  can be set all [spans] in project be like that
  set that span as global */
  :global(span) {
    /* can be accessed global css vars */
    background: var(--primaryColor);
    color: white;
  }

  /* global styles can be overriden locally
  with adding custom class to original class
  main-title svelte-sdfdffsfs  */
  .main-title{
    color: red;
  }
</style>
<span>
  hi from an example
  <!-- css comes from global
    will look exactly as needed -->
      <div class='main-title'>
        <h3>example title</h3>
      </div>
</span>



