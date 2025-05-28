<script lang="ts">
    const features: Record<string, string> = {
        "Collaboration Tools":
            "The ability to create and edit documents simultaneously with another user allows for an overall smoother experience.",
        "Online Status":
            "The online status feature will show if a user is online and what they're currently working on.",
        "File Download": "Being able to download files",
        "Alternative Themes":
            "Alternative themes allow users to choose whether or not they want to work with light or dark mode, allowing more comfort for late night workers.",
        "Private Spaces":
            "The private space gives users the ability to work on their own documents before deciding to share them or not.",
        "Personal Notes":
            "The notes feature is to allow users to make small notes whether it's a to-do list or a form of documentation.",
    };

    let selected = Object.keys(features)[0];

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
    <div class="wave-bg">
        <div class="about-container">
            <h2 class="about-title">
                <span>About</span>
                <br />
                <strong>Scribere</strong>
            </h2>
            <p class="about-description">
                <strong>Scribere is a cutting-edge collaborative document
                    editing platform designed to revolutionize knowledge sharing
                    and teamwork within organizations. Unlike many existing
                    platforms that fail to balance ease of use, security, and
                    real-time workflow integration, Scribere excels in all
                    three.<br>
                    With a secure, efficient, and intuitive workspace, it
                    enables teams to effortlessly create, edit, and manage
                    documents together in real time—boosting productivity,
                    enhancing collaboration, and ensuring seamless workflow
                    integration across your organization.</strong>
            </p>
        </div>
    </div>
</section>

<div class="banner">
    <img src="banner.png" alt="Try Scribere Today" />
</div>

<!-- FEATURES SECTION -->
<section id="features" class="features-section">
    <div class="wave-bg">
        <div class="features-container">
            <h2 class="features-title">
                <span>Special</span>
                <br />
                <strong>Features</strong>
            </h2>

            <div class="features-content">
                <ul class="features-list">
                    {#each Object.keys(features) as feature (feature)}
                        <li>
                            <button
                                class:selected={selected === feature}
                                onclick={() => (selected =
                                feature)}
                            >
                                {feature}
                            </button>
                        </li>
                    {/each}
                </ul>

                <div class="feature-description">
                    {features[selected]}
                </div>
            </div>
        </div>
    </div>
</section>

<section class="banner">
    <img src="banner2.png" alt="banner2" />
</section>

<!-- PRICING SECTION -->
<section id="pricing" class="pricing-section">
    <div class="wave-bg">
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
        </div>
    </div>
</section>

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

    .about-section, .features-section, .pricing-section {
        background-color: #2e3f4f;
        color: #fff;
        position: relative;
        height: 100vh;
        scroll-snap-align: start;
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 2rem;
        overflow: hidden;
    }

    .wave-bg {
        background-image: url("/Wave1.png");
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center;
        width: 120%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .about-container {
        max-width: 900px;
        padding: 2rem;
        text-align: left;
    }

    .about-title, .features-title, .pricing-title {
        font-size: 42px;
        font-weight: 400;
        line-height: 1.3;
        margin-bottom: 1.5rem;
    }

    .about-title strong, .features-title strong, .pricing-title strong {
        font-weight: 700;
    }

    .about-description, .feature-description {
        font-size: 1.1rem;
        line-height: 1.75;
        color: #f1f1f1;
    }

    .features-container {
        max-width: 1000px;
        padding: 2rem;
        text-align: left;
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

    .features-list {
        list-style: none;
        padding: 0;
        margin: 0;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .features-list button {
        background: none;
        border: none;
        font-size: 1rem;
        padding: 0.5rem 1rem;
        cursor: pointer;
        border-radius: 8px;
        color: #fff;
        text-align: left;
        font-weight: 300;
        min-width: 180px;
        transition: background-color 0.2s ease;
    }

    .features-list button:hover, .features-list button.selected {
        background-color: #f7bfa5;
        color: #000;
        font-weight: 300;
    }

    .feature-description {
        width: 400px;
        min-height: 140px;
        transition: opacity 0.3s ease;
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

    ul {
        margin-left: 1rem;
        text-align: left;
        display: inline-block;
    }

    .banner {
        width: 100vw;
        height: 900px;
        position: relative;
        left: 50%;
        right: 50%;
        margin-left: -50vw;
        margin-right: -50vw;
        overflow: hidden;
    }

    .banner img {
        width: 100%;
        height: 900px;
        display: block;
    }

    .pricing-content {
        display: flex;
        flex-direction: row;
        gap: 2rem;
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
        background-color: #e0f9f9;
        color: #2d3e50;
        border: none;
        border-radius: 0.75rem;
        padding: 1.5rem;
        width: 300px;
        height: 280px;
        box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        cursor: pointer;
        transition: transform 0.2s ease, box-shadow 0.2s ease;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        text-align: center;
    }

    .pricing-card:hover {
        transform: translateY(-6px);
        box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        font-weight: bolder;
    }

    .pricing-card h3 {
        font-size: 29px;
        font-weight: bold;
        margin-bottom: 0.5rem;
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
</style>
