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
<style>
    button {
        transition: 0.3s ease-in-out;
    border: none; /* Remove borders */
    padding: 15px 32px; /* Some padding */
    text-align: center; /* Centered text */
    text-decoration: none; /* Remove underline */
    font-size: 16px; /* Increase font size */
    margin: 4px 2px; /* Add some margin */
    cursor: pointer; /* Pointer cursor on hover */
    border-radius: 50px; /* Rounded corners */
    font-family: monospace;
    float:right;
    }
 </style>


{#if mode === "Light"}
<style>
    body {
        transition: 0.3s ease-in-out;
        background-color: white;
        color: #333;
    }
    button {
        transition: 0.3s ease-in-out;
        background-color:cornflowerblue; /* Green background */
        color: white; /* White text */
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
