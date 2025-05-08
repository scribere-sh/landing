<script lang="ts">
    import "../app.css";
    import type { LayoutProps } from "./$types";

    const { children }: LayoutProps = $props();
</script>

<div class="page-container">
    <nav>
        <div class="logo"><img src="ScribereLogo.png" alt="Logo" /></div>
        <div class="right-nav">
            <div class="nav-links">
                <a href="#about">ABOUT</a>
                <a href="#features">FEATURES</a>
                <a href="#pricing">PRICING</a>
            </div>
            <a class="go-to-app" rel="external" href="//app.scribere.sh"
            >GO TO APP</a>
        </div>
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
        color: #fff;
        font-weight: 800;
        font-size: 32px;
        font-family: monospace;
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
        flex: 1;
        overflow-y: auto;
        height: 100vh;
        padding-top: 70px;
        background-color: #000;
        color: #fff;

        /* Hide scrollbar visually */
        scrollbar-width: none; /* Firefox */
    }

    .content-container::-webkit-scrollbar {
        display: none; /* Chrome, Safari, Edge */
    }

    .right-nav {
        display: flex;
        gap: 1rem;
        align-items: center;
        margin-left: auto;
    }
</style>
