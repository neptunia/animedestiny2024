<script>
  import Footer from '$lib/components/Footer.svelte';
  import Navbar from '$lib/components/Navbar.svelte';

  import { onMount } from "svelte";

  let currentHash = ""; // to track the current anchor (e.g. #a, #b, etc.)

  // Function to check for the hash and apply glow effect
  function applyGlow() {
    const hash = window.location.hash;
    if (hash) {
      currentHash = hash; // update the reactive variable with the current hash

      setTimeout(() => {
        currentHash = ""; // Clear the glowing section after timeout
      }, 2000); // 2000 milliseconds = 2 seconds
    }
  }

  // Apply the glow effect when the page initially loads and when hash changes
  onMount(() => {
    applyGlow(); // check if the page is loaded with a specific hash

    window.addEventListener("hashchange", applyGlow); // listen for hash changes

    return () => {
      // Clean up when component is destroyed
      window.removeEventListener("hashchange", applyGlow);
    };
  });
</script>

<Navbar />

<main>

    <div class="page-title">
        Cosplay
    </div>

    <div class="page-body">
        <!-- <p style="font-family: 'Montserrat', sans-serif; font-size: 1.5rem; color: #485077; margin-bottom: 1rem;">To Be Announced - Stay Tuned!</p> -->
        
        <section class="content-section">
            <!-- <img 
                src="images/cosplay/cosplay_gathering.png" 
                alt="Cosplay Gathering Sign-Ups" 
                class="content-graphic"
            /> -->
            <div class="content-text">
                <h2>Cosplay!</h2>
                <p>
                    Showcase your cosplay talents at Anime Destiny 2026! Cosplays of all kinds from all fandoms are welcome; we encourage you to represent your favorite media and help bring the convention to life!
                    Please keep in mind a couple of ground rules for cosplay at Anime Destiny, since our event takes place on a University campus:
                </p>
                <ul style="list-style-type: square">
                        <li>Shoes must be worn at all times. Costumes should not be excessively revealing or impede traffic. No law enforcement or military uniforms allowed.</li> 
                        <li>No real or dangerous weapons are allowed. Prop weapons must be inspected at the front desk before being brought inside.</li> 
                        <li>
                            Full Rules: 
                            <a  
                            href="https://docs.google.com/document/d/18tocsvWVEZ8xFNBvz8-88AAK9CnIbqlU7jkXd4G_FvQ/edit?usp=sharing"
                            style="color: blue; text-decoration: underline;"
                            > 
                            Master Rules Document 
                        </a></li> </ul>
            </div>
        </section>

        <hr class="section-divider" />

        <section class="content-section">
            <!--
            <img 
                src="images/cosplay/cosplay_gathering.png" 
                alt="Cosplay Gathering Sign-Ups" 
                class="content-graphic"
            />
            -->
            <div class="content-text">
                <h2>Host a Cosplay Gathering!</h2>
                <p>
                    <strong>Interested in hosting a Cosplay Gathering? </strong>
                    We encourage you to connect with fellow fans from the same fandoms and create large cosplay groups at Anime Destiny! 
                    All are welcome to apply and submit a request for a gathering - no prior hosting experience needed!
                </p>
                <a 
                    href="https://forms.gle/4pbB5MdgpSSJBzQT7" 
                    class="signup-link"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Submit an application here
                </a>
                <p>A cosplay gathering schedule will be posted once requested gatherings are confirmed!</p>
            </div>
        </section>
        
        <hr class="section-divider" />

        <section class="content-section">
            <div class="content-text">
                <h2>Cosplay Contest</h2>
                <p>
                    <strong>Interested in participating in our Cosplay Contest? </strong>
                    Applications are open now all the way up until the time of the event! More information can be found in the form below~

                </p>
                <a 
                    href="https://forms.gle/BLnGZ3CQNWUokKDZA" 
                    class="signup-link"
                    target="_blank" 
                    rel="noopener noreferrer"
                >
                    Apply here
                </a>
                <p>Information about our judges and cosplay guests will be released soon!</p>
            </div>
        </section>

        <!--
        <section class="content-section">
            <img 
                src="images/cosplay/cosplay_template.jpg" 
                alt="Cosplay Line-Up" 
                class="content-graphic"
            />
            <div class="content-text">
                <h2>Show Off Your Cosplay Line-Up!</h2>
                <p>
                    Use this tag on your socials with the tag 
                    <strong>#animedestiny2025</strong> 
                    to show off your exciting cosplay for Anime Destiny!
                </p>
            </div>
        </section>
        -->

    </div>
</main>

<style>
    main {
        flex-grow: 1;
        display: flex;
        flex-direction: column;
    }

    .page-body {
        padding: 1rem;
        width: 100%;
        max-width: 100rem;
        margin: auto;
    }

    /* Added Styles for New Content */
    .content-section {
        display: flex;
        flex-wrap: wrap; /* Allows items to wrap on smaller screens */
        gap: 2rem; /* Adds space between image and text */
        align-items: center; /* Vertically centers items */
        margin-bottom: 2rem;
    }

    .content-graphic {
        flex: 1 1 300px; /* Allows graphic to grow/shrink, with a base of 300px */
        max-width: 100%; /* Ensures image is responsive */
        height: auto;
        object-fit: cover;
        border-radius: 8px; /* Optional: adds rounded corners */
        box-shadow: 0 4px 8px rgba(0,0,0,0.1); /* Optional: adds subtle shadow */
    }

    .content-text {
        flex: 2 1 400px; /* Allows text block to grow/shrink, with a larger base */
    }

    .content-text h2 {
        font-size: 1.75rem;
        color: #333;
        margin-bottom: 1rem;
    }

    .content-text p {
        font-size: 1.1rem;
        line-height: 1.6;
        margin-bottom: 1.5rem;
    }

    .signup-link {
        display: inline-block;
        padding: 0.75rem 1.5rem;
        background-color: #007bff; /* Example button color */
        color: #ffffff;
        text-decoration: none;
        font-weight: bold;
        border-radius: 5px;
        transition: background-color 0.3s ease;
    }

    .signup-link:hover {
        background-color: #0056b3; /* Darker blue on hover */
    }

    .section-divider {
        border: 0;
        height: 1px;
        background: #e0e0e0;
        margin: 2.5rem 0;
    }

    /* Reverse layout for the second item for visual variety */
    .content-section:nth-child(odd) {
         /* This will apply to the first .content-section */
         /* You could reverse it if you prefer: flex-direction: row-reverse; */
    }

    @media (max-width: 768px) {
        .content-section {
            flex-direction: column; /* Stacks image and text vertically */
        }
    }
</style>

<Footer/>