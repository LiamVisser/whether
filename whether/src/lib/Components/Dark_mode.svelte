<script>
    let mode = $state("Light");
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
        background-color:cornflowerblue;
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
    /* Base link style for dark mode */
a {
  color: #4dabf7; /* soft blue */
  text-decoration: none;
  transition: color 0.3s ease, text-shadow 0.3s ease;
}

/* Hover & focus effects */
a:hover,
a:focus {
  color: #74c0fc; /* lighter blue */
  text-shadow: 0 0 5px rgba(116, 192, 252, 0.5);
  outline: none;
}

/* Visited link */
a:visited {
  color: #9c8fff; /* slightly muted purple */
}

/* Active link (on click) */
a:active {
  color: #ffa94d; /* orange for contrast */
}

/* Optional underline on hover only */
a:hover {
  text-decoration: underline;
}
</style>
{/if}
