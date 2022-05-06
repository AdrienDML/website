<nav class="navcont">
    {#if show_hamb }
        <div class="hamcont">
            <svg viewBox="0 0 10 10" width="10" height="100%">
            </svg>
        </div>
    {/if}
    {#each routes as route, index}
        {#if index!=selected }
            <!-- svelte-ignore a11y-invalid-attribute -->
            <a href="#" on:click={() => selected = index}>{route}</a>
        {:else}
            <a href="#" class="selected" on:click={() => selected = index}>{route}</a>
        {/if}
    {/each}
</nav>

<script lang="ts">
    export let routes : Array<String>;
    export let show_hamb : boolean = false;
    let selected: number = 0;
</script>

<style>
    a {
        color: var(--fg);
        text-decoration: none;
        font-size: 1.5em;
        text-align: center;
        border-width: .2em;
        border-style: solid;
        border-color: rgba(0, 0, 0, 0);
        width: 90%;
    }

    .selected {
        color:var(--bg);
        background-color:var(--accent);
        border-color: var(--bg);
        border-radius: 1em;
    }

    .hamcont {
        height: 10px;
        aspect-ratio: 10px;
    }

    .navcont {
        margin: .5em 5%;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
        width: 90%;
        border: .2em solid var(--accent);
        border-radius: 2em;
    }
</style>
