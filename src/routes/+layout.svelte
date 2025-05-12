<script lang="ts">
    import "../app.css";
    import type { LayoutProps } from "./$types";

    const { children }: LayoutProps = $props();
</script>

<div class="page-container">
    <nav>
        <button
            type="button"
            class="logo"
            onclick={() => {
                window.scrollTo({ top: 0, behavior: "smooth" });
                window.location.hash = "home";
            }}
            style="background: none; border: none; padding: 0; cursor: pointer"
            aria-label="Scroll to top and go to home"
        >
            <img src="ScribereLogo.png" alt="Scribere Logo" />
        </button>

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
        background-color: #495867;
        padding: 16px 32px;
        height: 120px;
    }

    .logo img {
        width: 160px;
        height: 60;
        margin-left: 60px;
    }

    .nav-links {
        text-decoration: none;
        padding: 8px 16px;
        border-radius: 20px;
        color: #fff;
        font-weight: 100;
        font-size: 32px;
        font-family: monospace;
        transition: all 0.1s ease-in-out;
    }

    .nav-links a {
        text-decoration: none;
        padding: 8px 16px;
        border-radius: 20px;
        color: #fff;
        font-weight: 100;
        font-size: 32px;
        font-family: monospace;
        transition: all 0.1s ease-in-out;
    }

    .nav-links a:hover {
        font-weight: 800;
        text-decoration: underline;
    }

    .go-to-app {
        display: inline-block;
        background-color: #dff9ff;
        color: #000;
        padding: 0.75rem 1.5rem;
        border-radius: 8px;
        font-weight: bold;
        text-decoration: none;
        transition: background-color 0.1s ease-in-out;
        margin-left: 1rem;
        white-space: nowrap;
    }

    .go-to-app:hover {
        background-color: #edc9ff;
        text-decoration: underline;
    }

    .content-container {
        flex: 1;
        overflow-y: auto;
        height: 100vh;
        padding-top: 70px;
        background-color: #000;
        color: #fff;

        /* Hide scrollbar visually */
        scrollbar-width: none;
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
