<script lang="ts">
    // Your script here if needed for page-specific logic
</script>

<section id="about" class="section">
    <h2 class="section-title">ABOUT</h2>
    <p class="section-content">
        Scribere is a cutting-edge collaborative document editing platform
        designed to revolutionize knowledge sharing and teamwork within
        organizations.
    </p>
</section>

<section id="features" class="section">
    <h2 class="section-title">FEATURES</h2>
    <div class="feature-container">
        <div class="feature">
            <strong>COLLABORATION TOOLS</strong>
            <p>
                The ability to create and edit documents simultaneously with
                another user allows for an overall smoother experience.
            </p>
        </div>
        <div class="feature">
            <strong>ONLINE STATUS</strong>
            <p>
                The online status feature will show if a user is online and what
                they’re currently working on.
            </p>
        </div>
        <div class="feature">
            <strong>FILE DOWNLOAD</strong>
            <p>
                Being able to download files allows users to export important
                documents that need to be reviewed outside.
            </p>
        </div>
    </div>
</section>

<section id="pricing" class="section">
    <h2 class="section-title">PRICING</h2>
    <div class="pricing-container">
        <p><strong>Monthly</strong></p>
        <p><strong>Free Individual</strong> – Limited private space</p>
        <p><strong>Paid:</strong></p>
        <ul>
            <li>
                Tier 1 – 5 Spaces – Limited to 5 users online at once
                ($29/month)
            </li>
            <li>
                Tier 2 – 10 Spaces Each – Limited to 20 users online at once
                ($78/month)
            </li>
            <li>
                Tier 3 – 20 Spaces Each – Limited to 100 users online at once
                ($199/month)
            </li>
        </ul>
    </div>
</section>

<style scoped>
    /* Container for each section to handle white background */
    .section {
        background-color: #fff;
        color: #000;
        padding: 4rem 2rem;
        text-align: center;
        margin-bottom: 2rem;
    }

    /* Section Titles */
    .section-title {
        background-color: #d5fafa;
        display: inline-block;
        padding: 0.5rem 2rem;
        border-radius: 8px;
        color: #000;
        margin-bottom: 1.5rem;
    }

    /* Content inside each section */
    .section-content, .feature p, .pricing-container p {
        max-width: 800px;
        margin: 0 auto;
        line-height: 1.6;
        font-family: sans-serif;
    }

    .feature-container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 1rem;
        max-width: 900px;
        margin: 0 auto;
    }

    .feature {
        background-color: #fff;
        color: #000;
        padding: 1rem;
    }

    ul {
        margin-left: 1rem;
    }

    /* For responsiveness: Stack feature items on smaller screens */
    @media (max-width: 768px) {
        .feature-container {
            grid-template-columns: 1fr 1fr;
        }
    }

    @media (max-width: 480px) {
        .feature-container {
            grid-template-columns: 1fr;
        }
    }
</style>
