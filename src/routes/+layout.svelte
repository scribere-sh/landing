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
    .page-container {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
        background-color: #000;
        color: #fff;
        overflow: hidden;
    }

    nav {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 1000;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background-color: #1a1a1a;
        padding: 1rem 2rem;
        height: 70px;
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
        margin-left: auto;
    }

    .content-container {
        background-color: #fff;
        color: #000;
        flex: 1;
        overflow-y: scroll;
        height: 100vh;
        padding-top: 70px;
    }
</style>
