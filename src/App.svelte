<script>
    import Timer from "./Timer.svelte";
    import HowTo from "./HowTo.svelte";
    let audio;

    function timerEnds(e) {
        console.log(e);
        audio.play();
    }
</script>

<style>
    h1,h3 {
        text-align: center;
    }
</style>

<h1 class="is-primary">HWA</h1>

<Timer on:end = {timerEnds}/>
<HowTo />
<audio bind:this={audio} src="dlj.mp3"></audio>