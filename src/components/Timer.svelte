<script>
  import ProgressBar from "./ProgressBar.svelte";
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">seconds remain</h2>
</div>
<ProgressBar />
<div bp="grid">

<button class="start" bp="offset-5@md 4@md 12@sm"> Start </button>
</div>

<style>
  .start {
    background-color: greenyellow;
    width: 100%;
    margin: 10px 0;

  }
  h2 {
    margin: 0;
  }
</style>
