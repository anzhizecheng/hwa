<script>
    import ProgressBar from "./ProgressBar.svelte"
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
</style>

<ProgressBar />
<div bp="grid">
    <h2>Seconds Left.</h2>

</div>

<button class="start">Start</button>