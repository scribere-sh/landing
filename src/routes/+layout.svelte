<script lang="ts">
    import "../app.css";
    import { onMount } from "svelte";

    let menuOpen = false;

    // Optional: Close menu if window resized above breakpoint
    function handleResize() {
        if (window.innerWidth > 768) {
            menuOpen = false;
        }
    }

    onMount(() => {
        window.addEventListener("resize", handleResize);
        return () => window.removeEventListener("resize", handleResize);
    });
</script>

<svelte:head>
    <link rel="stylesheet" href="https://use.typekit.net/psh5enk.css" />
</svelte:head>

<div class="page-container">
    <nav>
        <button
            type="button"
            class="logo"
            on:click={() => {
                window.scrollTo({ top: 0, behavior: "smooth" });
                window.location.hash = "home";
            }}
            style="background: none; border: none; padding: 0; cursor: pointer"
            aria-label="Scroll to top and go to home"
        >
            <img src="ScribereLogo.png" alt="Scribere Logo" />
        </button>

        <!-- Hamburger button visible on small screens -->
        <button
            class="hamburger-btn"
            aria-label="Toggle menu"
            aria-expanded={menuOpen}
            on:click={() => (menuOpen = !menuOpen)}
        >
            <div class="bar"></div>
            <div class="bar"></div>
            <div class="bar"></div>
        </button>

        <div class="right-nav {menuOpen ? 'open' : ''}">
            <div class="nav-links">
                <a href="#about" on:click={() => (menuOpen = false)}>ABOUT</a>
                <a href="#features" on:click={() => (menuOpen = false)}
                >FEATURES</a>
                <a href="#pricing" on:click={() => (menuOpen = false)}
                >PRICING</a>
            </div>
            <a
                class="go-to-app"
                rel="external"
                href="//app.scribere.sh"
                on:click={() => (menuOpen = false)}
            >
                GO TO APP
            </a>
        </div>
    </nav>

    <div class="content-container">
        <slot />
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
        background-image: linear-gradient(#495867, #2d3740);
        padding: 16px 32px;
        height: 128px;
    }

    .logo img {
        width: 310px;
        height: 110px;
        margin-left: 60px;
    }

    /* Hamburger Button */
    .hamburger-btn {
        display: none;
        flex-direction: column;
        justify-content: space-between;
        width: 28px;
        height: 22px;
        background: none;
        border: none;
        cursor: pointer;
        padding: 0;
        margin-left: 1rem;
    }
    .hamburger-btn .bar {
        width: 100%;
        height: 3px;
        background-color: #fff;
        border-radius: 2px;
        transition: all 0.3s ease;
    }

    /* Right Nav */
    .right-nav {
        display: flex;
        gap: 1rem;
        align-items: center;
        margin-left: auto;
        transition: max-height 0.3s ease;
    }

    .nav-links {
        display: flex;
    }

    .nav-links a {
        text-decoration: none;
        padding: 8px 16px;
        border-radius: 20px;
        font-weight: 100;
        color: #fff;
        font-size: 32px;
        transition: all 0.1s ease-in-out;
    }

    .nav-links a:hover {
        font-weight: 500;
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
        scrollbar-width: none;
    }

    .content-container::-webkit-scrollbar {
        display: none;
    }

    /* Responsive */
    @media (max-width: 768px) {
        nav {
            padding: 8px 16px;
            height: 70px;
        }

        .logo img {
            width: 150px;
            height: 50px;
            margin-left: 10px;
        }

        /* Show hamburger */
        .hamburger-btn {
            display: flex;
        }

        /* Hide nav links by default */
        .nav-links {
            flex-direction: column;
            gap: 1rem;
        }

        /* Hide .right-nav by default (except hamburger) */
        .right-nav {
            position: fixed;
            top: 70px;
            right: 0;
            background-image: linear-gradient(#495867, #2d3740);
            flex-direction: column;
            width: 200px;
            max-height: 0;
            overflow: hidden;
            padding: 0 1rem;
            border-bottom-left-radius: 8px;
            border-bottom-right-radius: 8px;
            transition: max-height 0.3s ease;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }

        /* Show menu when open */
        .right-nav.open {
            max-height: 300px; /* enough for links */
            padding: 1rem;
        }

        .nav-links a {
            font-size: 18px;
            padding: 12px;
        }

        .go-to-app {
            margin-left: 0;
            margin-top: 1rem;
            width: 100%;
            text-align: center;
            padding: 0.75rem 0;
            font-size: 18px;
        }
    }
</style>
