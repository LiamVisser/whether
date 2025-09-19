<script>
    let mode = $state("Dark");
    function switchMode() {
        if (mode === "Dark")
        {
            mode = "Light";
        }
        else
        {
            mode = "Dark";
        }
        }
</script>

<button onclick={switchMode}>{mode} Mode</button>
{#if mode === "Light"}
<style>
    body {
        transition: 0.3s ease-in-out;
        background-color: white;
        color: #333;
    }
</style>
{:else}
<style>
    body {
        transition: 0.3s ease-in-out;
        background-color: #333;
        color: white;
    }
</style>
{/if}
