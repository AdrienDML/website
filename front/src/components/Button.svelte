<button>{label}</button>

<script lang="ts">
    export let label: string;
</script>

<style>
    button {
        background-color: var(--accent);       
        font-size: 1em;
        border: none;
        color: var(--fg);
        padding: 0.5em 1.5em;
        border-radius: 0.2em;
        transition: 0.2s;
    }

    button:hover {
        transform: scale(1.1);
    }

    button:active {
        background-color: var(--accent-dark);
    }
</style>
