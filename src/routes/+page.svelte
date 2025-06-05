<script lang="ts">
    // Features List
    const features: Record<string, string> = {
        "Collaboration Tools":
            "Work together and edit documents simultaneously for faster, smoother teamwork.",
        "Online Status":
            "Know who's online and what they're working on. Streamline communication and boost productivity.",
        "File Download":
            "Instantly download your files anytime, anywhere. No delays, no hassle.",
        "Alternative Themes":
            "Customize your experience with multiple themes tailored to your style and comfort.",
        "Private Spaces":
            "Stay in control with secure private spaces. Your documents, your eyes only.",
    };

    // Default selected feature
    let selected = Object.keys(features)[0];

    // Subcription Plans
    const plans = [
        {
            id: "free",
            tier: "Free Plan",
            description:
                "A free individual plan that is limited to private spaces",
            price: "$0.00",
        },
        {
            id: "tier1",
            tier: "Startup Plan",
            description: "5 Spaces\nLimited to 5 users",
            price: "$29.00",
        },
        {
            id: "tier2",
            tier: "Team Plan",
            description: "10 Spaces\nLimited to 20 users",
            price: "$78.00",
        },
        {
            id: "tier3",
            tier: "Business Plan",
            description: "20 Spaces\nLimited to 100 users",
            price: "$199.00",
        },
    ];
    const enterprise = [
        {
            id: "enterprise",
            tier: "Enterprise Plans",
            description:
                "For custom plans, please get in touch with our sales team",
            price: "Get in Touch",
        },
    ];
</script>

<!-- HERO SECTION -->
<section class="hero">
    <div class="hero-content">
        <h1>
            <span>Collaboration</span>
            <br />
            <strong>Redefined</strong>
        </h1>
        <a class="hero-button" href="//app.scribere.sh" rel="external"
        >GO TO APP</a>
    </div>
</section>

<!-- ABOUT SECTION -->
<section id="about" class="about-section">
    <div class="about-container">
        <h2 class="about-title">
            <span>About</span>
            <br>
            <strong>Scribere</strong>
        </h2>
        <p class="about-description">
            <strong>Scribere is a cutting-edge collaborative document editing
                platform designed to revolutionize knowledge sharing and
                teamwork within organizations. Unlike many existing platforms
                that fail to balance ease of use, security, and real-time
                workflow integration, Scribere excels in all three.<br><br>

                With a secure, efficient, and intuitive workspace, it enables
                teams to effortlessly create, edit, and manage documents
                together in real time—boosting productivity, enhancing
                collaboration, and ensuring seamless workflow integration across
                your organization.</strong>
        </p>
    </div>
</section>

<!-- BANNER ONE -->
<div class="banner">
    <img src="banner.png" alt="Try Scribere Today" />
</div>

<!-- FEATURES SECTION -->
<section id="features" class="features-section">
    <div class="features-container">
        <h2 class="features-title">
            <span>Special</span>
            <br />
            <strong>Features</strong>
        </h2>

        <div class="features-content">
            <!-- Feature List -->
            <ul class="features-list">
                {#each Object.keys(features) as feature (feature)}
                    <li>
                        <button
                            class:selected={selected === feature}
                            onclick={() => (selected = feature)}
                        >
                            {feature}
                        </button>
                    </li>
                {/each}
            </ul>

            <!-- Feature Detail -->
            <div class="feature-description">
                {features[selected]}
            </div>
        </div>
    </div>
</section>

<!-- BANNER TWO -->
<section class="banner2">
    <img src="banner2.png" alt="banner2" />
</section>

<!-- PRICING SECTION -->
<section id="pricing" class="pricing-section">
    <div class="pricing-container">
        <h2 class="pricing-title">
            <span>Monthly</span>
            <br>
            <strong>Pricing</strong>
        </h2>

        <div class="pricing-content">
            <div class="cards">
                {#each plans as plan (plan.id)}
                    <a href="/this-is-a-uni-project" class="pricing-card">
                        <h3>{plan.tier}</h3>
                        <span class="description">{plan.description}</span>
                        <span class="price">{plan.price}</span>
                    </a>
                {/each}
            </div>
        </div>
        <br>
        <br>
        <div class="enterprise-content">
            <div class="enterprise-cards">
                {#each enterprise as enterprise (enterprise.id)}
                    <a href="/this-is-a-uni-project" class="enterprise-card">
                        <h3>{enterprise.tier}</h3>
                        <span class="description">{
                            enterprise.description
                        }</span>
                        <span class="price">{enterprise.price}</span>
                    </a>
                {/each}
            </div>
        </div>
    </div>
</section>

<!-- LEGAL FOOTER -->
<footer class="legal-footer">
    <div class="footer-container">
        <p>&copy; {new Date().getFullYear()} Scribere. All rights reserved.</p>
        <nav class="footer-links">
            <a href="/this-is-a-uni-project">Terms of Service</a>
            <a href="/this-is-a-uni-project">Privacy Policy</a>
            <a href="/this-is-a-uni-project">Contact Us</a>
        </nav>
    </div>
</footer>

<!-- BACK TO TOP -->
<button
    type="button"
    class="back-to-top"
    onclick={() => {
        window.scrollTo({ top: 0, behavior: "smooth" });
        window.location.hash = "home";
    }}
    aria-label="^Back to top"
>
    BACK TO TOP
</button>

<!-- CSS BELOW -->
<style scoped>
    .hero {
        background-image: url("/Hero-BG.png");
        background-size: cover;
        background-position: center;
        height: 100vh;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        padding: 0 5%;
    }

    .hero-content {
        color: white;
        max-width: 600px;
    }

    .hero-content h1 {
        font-size: 97px;
        line-height: 1.2;
        margin-bottom: 1.5rem;
    }

    .hero-content h1 strong {
        font-weight: 850;
    }

    .hero-button {
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

    .about-section, .features-section {
        background: url("/Wave1.png"), linear-gradient(#4a5e6e, #364552);
        background-size: cover;
        background-position: center;
        height: 100vh;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        color: #fff;
        position: relative;
        scroll-snap-align: start;
        padding: 260px;
        overflow: hidden;
    }

    .pricing-section {
        background: url("/Wave1.png"), linear-gradient(#4a5e6e, #364552);
        background-size: cover;
        background-position: center;
        color: #fff;
        position: relative;
        height: 100vh;
        scroll-snap-align: start;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 260px;
        overflow: hidden;
    }

    .about-container {
        max-width: 1200px;
        padding: 2px;
        text-align: left;
    }

    .about-title, .features-title, .pricing-title {
        font-size: 48px;
        font-weight: 400;
        line-height: 1.3;
        margin-bottom: 1.5rem;
    }

    .pricing-title {
        padding-top: 10rem;
    }
    .about-title strong, .features-title strong, .pricing-title strong {
        font-weight: 700;
        font-size: 65px;
    }

    .about-description, .feature-description {
        font-size: 1.1rem;
        line-height: 1.75;
        color: #f1f1f1;
        font-size: 24px;
    }

    .features-container {
        max-width: 1000px;
        padding: 5px;
        text-align: left;
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .features-content {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        flex-wrap: wrap;
        justify-content: center;
        align-items: flex-start;
        min-height: 250px;
    }

    @media (max-width: 768px) {
        .features-content {
            flex-direction: column;
            align-items: center;
        }

        .feature-description {
            text-align: center;
        }
    }

    .features-list {
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        list-style: none;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .features-list button {
        text-align: center;
        background: none;
        border: none;
        font-size: 24px;
        padding: 0.5rem 1rem;
        cursor: pointer;
        border-radius: 8px;
        color: #fff;
        text-align: left;
        font-weight: 300;
        min-width: 180px;
        transition: background-color 0.1s ease;
    }

    .features-list button:hover, .features-list button.selected {
        background-color: #f7bfa5;
        color: #000;
    }

    .feature-description {
        display: flex;
        width: 500px;
        min-height: 140px;
        transition: opacity 0.3s ease;
    }

    ul {
        margin-left: 1rem;
        text-align: left;
        display: inline-block;
    }

    .banner {
        width: 100vw;
        height: 720px;
        position: relative;
        left: 50%;
        right: 50%;
        margin-left: -50vw;
        margin-right: -50vw;
        overflow: hidden;
    }

    .banner img {
        width: 100%;
        height: 720px;
        display: block;
    }

    .banner2 {
        width: 100vw;
        height: 960px;
        position: relative;
        left: 50%;
        right: 50%;
        margin-left: -50vw;
        margin-right: -50vw;
        overflow: hidden;
    }

    .banner2 img {
        width: 100%;
        height: 960px;
        display: block;
    }

    .pricing-content {
        display: flex;
        flex-direction: row;
        gap: rem;
        flex-wrap: wrap;
        justify-content: center;
        align-items: flex-start;
        min-height: 250px;
    }

    .pricing-content a {
        text-decoration: none;
    }

    .cards {
        display: flex;
        flex-wrap: wrap;
        gap: 1.5rem;
        justify-content: center;
    }

    .pricing-card {
        border-radius: 10px;
        background: #e0f9f9;
        padding: 2rem;
        width: 300px;
        height: 280px;
        cursor: pointer;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        box-shadow: 0 0 5px 0px #e0f9f9;
        text-decoration: none;
        color: #2d3e50;
        transition: transform 0.2s ease;
    }

    .pricing-card:hover {
        transform: translateY(-6px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        font-weight: bolder;
    }

    .pricing-card h3 {
        font-size: 29px;
        font-weight: bold;
        margin-bottom: 1.5rem;
    }

    .description {
        font-size: 21px;
        flex-grow: 1;
        display: flex;
        align-items: center;
        justify-content: center;
        line-height: 1.3;
        margin: 0.5rem 0;
        white-space: pre-wrap;
    }

    .price {
        background-color: #f2b8a2;
        color: #333;
        font-weight: bolder;
        font-size: 22px;
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
    }

    .enterprise-content {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        flex-wrap: wrap;
        justify-content: left;
        align-items: flex-start;
        min-height: 250px;
    }

    .enterprise-content a {
        text-decoration: none;
    }

    .enterprise-cards {
        display: flex;
        flex-wrap: wrap;
        gap: 1.5rem;
        justify-content: left;
    }

    .enterprise-card {
        border-radius: 10px;
        background: #e0f9f9;
        padding: 2rem;
        width: 1275px;
        height: 167px;
        cursor: pointer;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: left;
        box-shadow: 0 0 5px 0px #e0f9f9;
        text-decoration: none;
        color: #2d3e50;
        transition: transform 0.2s ease;
    }

    .enterprise-card:hover {
        transform: translateY(-6px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        font-weight: bolder;
    }

    .enterprise-card h3 {
        font-size: 29px;
        font-weight: bold;
        margin-bottom: 0.5rem;
    }

    .legal-footer {
        background-color: #1a1a1a;
        color: #ccc;
        padding: 1.5rem;
        text-align: center;
        font-size: 0.9rem;
    }

    .legal-footer {
        background: linear-gradient(#4a5e6e, #364552);
        color: #ccc;
        padding: 1.5rem;
        text-align: center;
        font-size: 0.9rem;
    }

    .footer-container {
        max-width: 960px;
        margin: 0 auto;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        align-items: center;
    }

    .footer-links {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        gap: 1rem;
    }

    .footer-links a {
        color: #ccc;
        text-decoration: none;
        transition: color 0.2s ease;
    }

    .footer-links a:hover {
        color: #fff;
    }
</style>
