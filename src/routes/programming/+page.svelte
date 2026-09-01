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
    Programming
  </div>

  <div class="page-body">
  <p style="font-family: 'Montserrat', sans-serif; font-size: 1.5rem; color: #485077; margin-bottom: 1rem;">To Be Announced - Stay Tuned!</p>

    <!-- 5th Floor - Tilden Room -->
    <!--
    <section id="tilden-room">
      <h2>5th Floor - Tilden Room</h2>

      <!-- Panels -->
      <div class="panel-category">
        <!--<h3>Panels</h3>-->

        <!-- <section id="panel-template" class="program-card" class:glow={currentHash === "#panel-template"}>
          <div class="name-bar"><h4></h4></div>
           <p><strong>Location:</strong> Tilden Room Patio</p>
          <p><strong>Time:</strong> 10:00 AM - 10:30 AM</p>
          <p>This is Issei Band, a band consisting of members that are all in UC Berkeley’s Japanese Language program. They will be performing hit songs from anime and J-pop culture; please enjoy! The performance will kick-off Anime Destiny 2025 and end with a special word from our Director!</p>
          <div class="issei-band-image">
            <img src="images\Anime Destiny 2025 - Issei Band (3).png" alt="Work in Progress" />
          </div>
        </section>
      </div>
      -->
  
</main>

<style>
  main {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }

  h2 {
    font-size:2em;
  }

  h3 {
    font-size:1.5em;
  }

  .program-card {
    background-color: #f9f9f9;
    border: 2px solid #1d3557;
    padding: 0 1rem 1rem 1rem;
    border-radius: 8px;
    transition: box-shadow 0.3s ease, transform 0.3s ease;
    text-align: left;
    max-width: 100rem;
    margin-bottom:0.5rem;
    margin-top:0.5rem;
  }

  .program-card:hover {
    box-shadow: 0 0 10px 3px rgba(29, 53, 87, 0.5); /* Slight glow */
    transform: translateY(-3px); /* Slight lift */
  }

  .glow {
    box-shadow: 0 0 10px 3px rgba(29, 53, 87, 0.5); /* Slight glow */
    transform: translateY(-3px); /* Slight lift */
  }

  /* Name bar styling */
  .name-bar {
    display: flex;
    align-items: center;
    background-color: #1d3557; /* Blue background */
    color: white;
    width: 100%; /* Full width of the card */
    padding: 1rem;
    margin-bottom: 10px; /* Add space below the name */
    width: calc(100% + 2rem); /* Full width + compensate for side padding */
    margin-left: -1rem;
  }

  .page-body {
      
      padding: 1rem;
      width: 100%;
      max-width: 100rem;
      margin: auto;
    }
    p {
      margin-bottom: 1rem;
    }

  .link {
    color: #485077;
    text-decoration: none;
    border-bottom: 1px solid #485077; /* Underline links */
    transition: color 0.3s ease, border-bottom-color 0.3s ease;
    word-wrap: break-word;
    font-weight: bold;
  }

  .link:hover {
    color: #fed893; /* Yellow on hover */
    border-bottom-color: #fed893;
  }

  /* Step 1: Combine all your repetitive image styles into one */
  .image-wrapper img {
    max-width: 200px;
    max-height: 200px;
    padding: 5px;
    height: auto; /* Use auto for better responsive scaling */
  }

  /* Step 2: Create a flex container for the card's content */
  .card-content {
    display: flex;
    flex-direction: row; /* Arrange items side-by-side */
    gap: 1rem; /* Add space between text and image */
  }

  /* Step 3: Define the text wrapper to take up half the space */
  .text-wrapper {
    flex: 1; /* Allows the text block to grow */
    max-width: 50%; /* Restricts it to half the container's width */
  }

  /* Step 4: Define the image wrapper */
  .image-wrapper {
    display: flex;
    justify-content: flex-end; /* Align image to the right */
    flex: 1; /* Allows the image block to grow */
  }

  .guess-song-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .nene-qna-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .nikkei-choral-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .jpop-kpop-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .shipgirls-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .himeko-firefly-container {
    display: flex;
    justify-content: center;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px 50px;
  }

  .himeko-firefly-image img {
    height: 300px;
  }

  .genshin-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .issei-band-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .cosplay-competition-101-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .cosplay-comp-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .otaku-ongaku-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .wotagei-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .intermission-container {
    display: flex;
    justify-content: center;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px 50px;
  }

  .intermission-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  .virtual-bears-image img {
    max-width:300px;
    max-height:300px;
    margin:0 auto;
    padding: 5px;
  }

  /* Responsive Styles */
  @media (max-width: 1024px) {
    .video-container iframe {
      height: 400px; /* Adjust height for tablets */
      width: 100%;
    }
  }

  @media (max-width: 768px) {
    .video-container iframe {
      height: 300px; /* Adjust height for mobile screens */
      width: 100%;
    }
  }

  @media (max-width: 480px) {
    .video-container iframe {
      height: 200px; /* Adjust height for small mobile screens */
      width: 100%;
    }
  }
</style>
  
  <Footer/>
