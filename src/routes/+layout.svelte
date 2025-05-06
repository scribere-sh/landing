<script lang="ts">
    import "../app.css";
    import type { LayoutProps } from "./$types";

    const { children }: LayoutProps = $props();
</script>

<div class="page-container">
    <nav>
        <div class="logo"><img src="ScribereLogo.png" alt="Logo"></div>
        <div class="nav-links">
            <a href="#about">About</a>
            <a href="#features">Features</a>
            <a href="#pricing">Pricing</a>
        </div>
        <a class="go-to-app" rel="external" href="//app.scribere.sh"
        >GO TO APP</a>
    </nav>

    <div class="content-container">
        {@render children()}
    </div>
</div>

<style scoped>
    /* Styles for page-container */
    .page-container {
        display: flex;
        flex-direction: column;
        min-height: 100vh; /* Ensure full height of the viewport */
        background-color: #000; /* Black background for the page */
        color: #fff; /* White text for overall page */
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #1a1a1a;
        padding: 1rem 2rem;
    }

    .logo img {
        width: 150px;
    }

    .nav-links {
        display: flex;
        gap: 1rem;
        align-items: center;
    }

    .nav-links a {
        text-decoration: none;
        padding: 0.5rem 1rem;
        border-radius: 20px;
        background-color: #f7bfa5;
        color: #000;
        font-weight: 600;
    }

    .go-to-app {
        text-decoration: none;
        padding: 0.5rem 1rem;
        border-radius: 20px;
        background-color: #f7bfa5;
        color: #000;
        font-weight: 600;
        margin-left: auto; /* Align to the right */
    }

    /* Content container with white background */
    .content-container {
        background-color: #fff; /* White background for content */
        color: #000; /* Black text inside the white container */
        padding: 2rem;
        flex: 1; /* Allow content to take up remaining space */
    }
</style>
