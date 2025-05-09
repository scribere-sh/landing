<script lang="ts">
    /* SCROLL BACK ON RELOAD */
    /*import { onMount } from "svelte";

    onMount(() => {
        if ("scrollRestoration" in history) {
            history.scrollRestoration = "manual";
            history.replaceState(null, "", "#home");
        }
        window.scrollTo(0, 0);
    });*/
</script>

<!-- HERO SECTION -->
<section class="hero">
    <div class="hero-content">
        <h1>
            <span>Collaboration</span>
            <br>
            <strong>Redefined</strong>
        </h1>
        <a class="hero-button" href="//app.scribere.sh" rel="external"
        >GO TO APP</a>
    </div>
</section>

<!-- ABOUT SECTION -->
<section id="about" class="section">
    <div class="about">
        <h1>
            <span>About</span>
            <br>
            <strong>Scribere</strong>
        </h1>
        <p class="section-content">
            Scribere is a cutting-edge collaborative document editing platform
            designed to revolutionize knowledge sharing and teamwork within
            organizations. Unlike many existing platfoms that fail to balance
            ease of use, security, and real-time workflow integration, Scribere
            excels in all three.
            <br>With a secure, efficient, and intuitive workspace, it enables
            teams to effortlessly create, edit, and manage documents together in
            real time—boosting productivity, enhancing collaboration, and
            ensuring seamless workflow integration across your organization.
        </p>
    </div>
</section>

<!-- FEATURES SECTION -->
<section id="features" class="section">
    <h2 class="section-title">FEATURES</h2>
    <div class="feature-container">
        <div class="feature">
            <strong>COLLABORATION TOOLS</strong>
            <p>Real-time editing and communication.</p>
        </div>
        <div class="feature">
            <strong>ONLINE STATUS</strong>
            <p>See who's online and what they're working on.</p>
        </div>
        <div class="feature">
            <strong>FILE DOWNLOAD</strong>
            <p>Download important documents for offline use.</p>
        </div>
        <div class="feature">
            <strong>ALTERNATIVE THEMES</strong>
            <p>Customize your interface with theme options.</p>
        </div>
        <div class="feature">
            <strong>PERSONAL NOTES</strong>
            <p>Private annotations and quick notes.</p>
        </div>
        <div class="feature">
            <strong>PRIVATE SPACES</strong>
            <p>Secure workspaces for departments or projects.</p>
        </div>
    </div>
</section>

<!-- PRICING SECTION -->
<section id="pricing" class="section">
    <h2 class="section-title">PRICING</h2>
    <div class="pricing-container">
        <p><strong>Monthly</strong></p>
        <p><strong>Free Individual</strong> - Limited private space</p>
        <p><strong>Paid:</strong></p>
        <ul>
            <li>Tier 1 - 5 Spaces - 5 users max ($29/month)</li>
            <li>Tier 2 - 10 Spaces - 20 users max ($78/month)</li>
            <li>Tier 3 - 20 Spaces - 100 users max ($199/month)</li>
        </ul>
        <p>
            <strong>Additional Charges:</strong>
            <br />
            $0.20 per extra active user/min over the limit.<br />
            100 GB extra shared space on all tiers.
        </p>
    </div>
</section>

<!-- STATIC "BACK TO TOP" BUTTON -->
<button
    type="button"
    class="back-to-top"
    onclick={() => {
        window.scrollTo({ top: 0, behavior: "smooth" });
        window.location.hash = "home";
    }}
    aria-label="Back to top"
>
    Back to Top
</button>

<style scoped>
    .hero {
        background-image: url("/Hero-BG.png");
        background-size: cover;
        background-position: center;
        height: 100vh;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        text-align: left;
        padding: 0 5%;
    }

    .about {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        text-align: left;
        padding: 0 5%;
    }

    .about h1 {
        font-size: 39px;
        font-weight: 200;
        line-height: 1.2;
        margin-bottom: 24px;
        font-family: monospace;
    }

    .about h1 strong {
        font-size: 39px;
        font-weight: 300;
        line-height: 1.2;
        margin-bottom: 1.5rem;
        font-family: monospace;
    }

    .hero-content {
        color: white;
        max-width: 600px;
    }

    .hero-content h1 {
        font-size: 97px;
        font-weight: 300;
        line-height: 1.2;
        margin-bottom: 1.5rem;
        font-family: monospace;
    }

    .hero-content h1 strong {
        font-size: 97px;
        font-weight: 700;
    }

    .hero-button {
        display: inline-block;
        background-color: #dff9ff;
        color: #000;
        padding: 0.75rem 1.5rem;
        border-radius: 8px;
        font-weight: bold;
        text-decoration: none;
        transition: background-color 0.1s ease-in-out;
    }

    .hero-button:hover {
        background-color: #edc9ff;
        text-decoration: underline;
    }

    .section {
        background-color: #000;
        color: #fff;
        padding: 64px 32px;
        text-align: center;
        height: 100vh;
        scroll-snap-align: start;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .section-title {
        background-color: #000;
        color: white;
        display: inline-block;
        padding: 8px 32px;
        border-radius: 10px;
        margin-bottom: 12px;
    }

    .section-content, .feature p, .pricing-container p {
        max-width: 800px;
        margin: 0 auto;
        line-height: 1.6;
        font-family: sans-serif;
    }

    .feature-container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 16px;
        max-width: 900px;
        margin: 0 auto;
    }

    .feature {
        background-color: #000;
        color: #fff;
        padding: 16px;
        border: 1px solid #ccc;
        border-radius: 8px;
    }

    .back-to-top {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background-color: #f7bfa5;
        color: #000;
        border: none;
        padding: 0.75rem 1.25rem;
        border-radius: 8px;
        font-weight: bold;
        cursor: pointer;
        z-index: 999;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        transition: background-color 0.1s ease-in-out;
    }

    .back-to-top:hover {
        background-color: #edc9ff;
        text-decoration: underline;
    }

    ul {
        margin-left: 1rem;
        text-align: left;
        display: inline-block;
    }

    @media (max-width: 768px) {
        .feature-container {
            grid-template-columns: 1fr 1fr;
        }

        .hero-content h1 {
            font-size: 2.2rem;
        }

        .hero-content h1 strong {
            font-size: 2.7rem;
        }
    }

    @media (max-width: 480px) {
        .feature-container {
            grid-template-columns: 1fr;
        }

        .hero-content h1 {
            font-size: 1.8rem;
        }

        .hero-content h1 strong {
            font-size: 2.2rem;
        }
    }
</style>
