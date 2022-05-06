<script lang="ts">
    import Button from "./components/Button.svelte";
    import NavBar from "./components/NavBar.svelte";
    let routes: Array<String> = [
        "Home",
        "Articles",
        "Courses",
        "ShowCase",
    ];
</script>

<header>
    <NavBar routes={routes}/>
</header>
<main>
    <!-- insert icon -->
    <h2 style="grid-area: name;">Adrien DM</h2>
    <div class="vertbar"></div>
    <p style="grid-area:intro">
        Hello I'm Adrien aka AdrienDML.
        I'm a french computer science student. 
        I like goofing around in rust and game developpement.
        I also do music and skateboarding as my hobbies.
    </p>
</main>
<footer style='grid-area:footer;'>
    <section class="contacts">
        <h1>Contacts</h1>
        <ul>
            <li>Twitter</li>
            <li>Twitch</li>
            <li>Redit</li>
            <li>Mastodon</li>
        </ul>
    </section>
</footer>

<style>
    :global(:root) {
        font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
            Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
        --bg: rgb(46, 52, 64);
        --fg: rgb(198, 201, 202);
        --accent: rgb(106, 194, 223);
        --accent-dark: #0190B3;
    }

    :global(body) {
        display: grid;
        grid-template-areas: "nav" "main" "footer";
        grid-template-rows: max-content 1fr max-content;
        background-color: var(--bg);
        font-size: 1.2rem;
    }
    
    :global(p) {
        width: min(70ch, 100%);
    }

    main {
        margin: 0 20%;
        margin-top: 20px;
        display: grid;
        grid-area: main;
        grid-template-areas: 
            "icon sep intro"
            "name sep intro"
            "cont cont cont";
        grid-template-rows: max-content max-content;
        grid-gap: 1em;
        color: var(--fg);
    }

    .vertbar {
        background-color: var(--fg);
        grid-area: sep;
        height: 100%;
        width: .3em;
        border-radius: .15em;
    }

    .contacts {
        display: flex;
        justify-content: center;
        align-items: center;
        color: var(--bg);
        background-color: var(--accent);
    }
</style>
