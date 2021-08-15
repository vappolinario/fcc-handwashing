<script>
    import ProgressBar from './ProgressBar.svelte';

    const totalSeconds = 20;
    let secondsLeft =  totalSeconds;
    let isRunning = false;

    $: progress = (1-(secondsLeft/totalSeconds)) * 100;

    function startTimer() {
        isRunning = true;
        const timer = setInterval(() => {
            secondsLeft -= 1;
            if (secondsLeft == 0) {
                clearInterval(timer)
                secondsLeft = totalSeconds;
                isRunning=false;
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
        background-color: #cccccc;
        cursor: not-allowed;
    }
</style>

<div bp="grid">
    <h2 bp="offset-5@md 4@md 12@sm" >Seconds Left: {secondsLeft}</h2>
</div>

<ProgressBar {progress} />

<div bp="grid">
    <button bp="offset-5@md 4@md 12@sm" class="start" type="submit" on:click={startTimer} disabled={isRunning}>Start</button>
</div>

