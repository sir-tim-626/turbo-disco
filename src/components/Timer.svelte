<script>
  import ProgressBar from "./ProgressBar.svelte";

  const totalSeconds = 20;
  let secondsLeft = totalSeconds;
  $: progress = (1 - secondsLeft / totalSeconds) * 100;

  let isRunning = false;
  function startTimer() {
    isRunning = true;

    const timer = setInterval(() => {
      secondsLeft -= 1;
      if (secondsLeft <= 0) {
        clearInterval(timer);
        secondsLeft = totalSeconds;
        isRunning = false;
      }
    }, 1000);
  }
</script>

<div bp="grid">
  <h2 bp="offset-5@md 4@md 12@sm">{secondsLeft} seconds remain</h2>
</div>
<ProgressBar {progress} />

<div bp="grid">
  <button
    disabled={isRunning}
    on:click={startTimer}
    class="start"
    bp="offset-5@md 4@md 12@sm"> Start </button>
</div>

<style>
  .start {
    background-color: greenyellow;
    width: 100%;
    margin: 10px 0;
  }
  .start[disabled] {
    background-color: grey;
    cursor: not-allowed;
  }
  h2 {
    margin: 0;
  }
</style>
