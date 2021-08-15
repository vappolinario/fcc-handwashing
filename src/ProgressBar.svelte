<script>
    export let progress = 20;
</script>

<style>
    .progress-container {
        margin: 20px 0;
        border: solid #f6f6f6
    }
    .progress-bar {
        height:30px;
        background-color: #ccffcc
    }
</style>

<div bp="grid">
    <div bp="offset-5@md 4@md 12@sm" class="progress-container">
        <div class="progress-bar" style="width: {progress}%;">
            <span class="sr-only">{progress}%</span>
        </div>
    </div>
</div>
