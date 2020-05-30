<script>
    import { createEventDispatcher } from "svelte"
  import ProgressBar from "./ProgressBar.svelte";
  const totalSecond = 6;
  let secondLeft = totalSecond;
  let isRunning = false;
    $:progress = 100 * (totalSecond - secondLeft)/totalSecond;
    const dispatch = createEventDispatcher();


  function startTimer() {
    let timer = setInterval(() => {
        isRunning = true;
      secondLeft -= 1;
      if (secondLeft == 0) {
        clearInterval(timer);
        isRunning = false;
        secondLeft = totalSecond;
        dispatch("end","timer end")
      }
    }, 1000);
  }
</script>

<style>
  h2 {
    margin: 0;
  }
  .start {
    background-color: rgb(154, 73, 73);
    width: 100%;
    margin: 10px 0;
  }
  .start[disabled] {
      background-color: rgb(194, 194, 194);
      cursor: not-allowed;
  }
</style>
<h1>{progress}</h1>
<ProgressBar progress = {progress}/>

<div bp="grid">
  <h2>{secondLeft} Seconds Left.</h2>
</div>

<div>
  <button disabled={isRunning} class="start" on:click={startTimer}>Start</button>
</div>
