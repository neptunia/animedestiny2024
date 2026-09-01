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
    Exhibitions
  </div>

  <div class="page-body">
    <p style="font-family: 'Montserrat', sans-serif; font-size: 1.5rem; color: #485077; margin-bottom: 1rem;">To Be Announced - Stay Tuned!</p>
    <!-- Kerr Lobby -->
    <!--
    <section id="kerr-lobby">
      <h2>3rd Floor - Kerr Lobby</h2>

      <section id="vfleet" class="program-card" class:glow={currentHash === "#vfleet"}>
          <div class="name-bar"><h4>VFleet and Indie VTuber Meet-and-Greets</h4></div>
          <p><strong>Location:</strong> Kerr Lobby</p>
          <p><strong>Time:</strong> All Day</p>
          <p>VTubers are taking over Anime Destiny! Visit the booth of our sponsor, VFleet Project, as they bring their cast of VTubers along with numerous other Indie VTubers for exclusive meet-and-greet opportunities! Also stop by the booth to learn more about VFleet and their mission involving ships and aircraft museums!</p>
          <p style="text-align: center; font-weight: bold;">VTuber Meet and Greets</p>
          <p>
            10:00AM - Josie-12 (M&amp;G)<br>
            10:30AM - Eve-80, Lina-55 (M&amp;G)<br>
            11:00AM - Anthony Talon (M&amp;G); Eve-80, Mayhem (iPad)<br>
            11:30AM - AlienMixture, PillowDear (M&amp;G)<br>
            12:00PM - Hara Rae Sol, Radiactive (M&amp;G)<br>
            12:30PM - Mim, RIHSURI (M&amp;G)<br>
            1:00PM - Nemimi Yane, Luci-04, LAZULI (M&amp;G); TRiGGERPHiSH (iPad)<br>
            1:30PM - Nene Amano, Camizole Corzette (M&amp;G)<br>
            <em>Note: Nene Amano’s meet-and-greet will be first-come, first-served; claim your ticket at registration by mentioning you are here for Nene (limit first ~30-35 people)</em><br>
            2:00PM - Prawn Star Itsi, Utano Pandora (M&amp;G)<br>
            2:30PM - Ali-60, Munii Shoda (M&amp;G)<br>
            3:00PM - Kat-14, FA.ye-18, TRiGGERPHiSH (M&amp;G), Estelle, Nemimi Yane (iPad)<br>
            3:30PM - Vampirate Odessa, Ami-35 (M&amp;G)<br>
            4:00PM - Mayhem (M&amp;G)<br>
            4:30PM - Lexie-16 (M&amp;G)<br>
            5:00PM - Daiya Fortuna, Estelle, Snoozy (M&G), RIHSURI (iPad)<br>
            5:30PM - Raki Kazuki (M&amp;G)
          </p>
          <div class="guess-song-image">
            <img src="images\exhibition\vfleet.png" alt="Work in Progress" />
          </div>
        </section>

      <section id="pixiv" class="program-card" class:glow={currentHash === "#pixiv"}>
          <div class="name-bar"><h4>pixiv Drawing Panel</h4></div>
          <p><strong>Location:</strong> Kerr Lobby</p>
          <p><strong>Time:</strong> All Day</p>
          <p>Come doodle on pixiv's drawing panel! Draw anything you want (as long as it's appropriate) and show off your creative flair at Anime Destiny. The panel will also be shared with pixiv for posting on their social media, so be sure to contribute to the panel! 
            Note: Please be respectful of other people's drawings and experiences, we may have to remove inappropriate drawings or otherwise improper additions, as needed.</p>
          <div class="guess-song-image">
            <img src="images\exhibition\pixiv.png" alt="Work in Progress" />
          </div>
        </section>

      <section id="neon-shrine" class="program-card" class:glow={currentHash === "#neon-shrine"}>
          <div class="name-bar"><h4>Neon Shrine</h4></div>
          <p><strong>Location:</strong> Kerr Lobby</p>
          <p><strong>Time:</strong> All Day</p>
          <p>Neon Shrine is a group specializing in goods for VTubers and Idols, such as penlights, happi coats, muffler towels, uchiwa fans, shikishi autograph boards, holographic tickets, and more! Come check them out and purchase some merch for your favorite VTubers, including SanFlare's Peoni Astera and indie Utano Pandora!</p>
          <div class="guess-song-image">
            <img src="images\exhibition\neon.png" alt="Work in Progress" />
          </div>
        </section>
    </section>
    -->

    <!-- Kerr Lobby -->
    <!--
    <section id="kerr-lobby">
      <h2>3rd Floor - Pauley Ballroom</h2>

      <section id="autographs" class="program-card" class:glow={currentHash === "#autographs"}>
          <div class="name-bar"><h4>Autographs with Analesa Fisher and Cia Court</h4></div>
          <p><strong>Location:</strong> Pauley Ballroom Booth 1</p>
          <p><strong>Time:</strong> 11:00 AM - 2:00 PM, 4:00 PM - 6:00 PM</p>
          <p>Special Guest voice actors Analesa Fisher and Cia Court will be doing autographing at Anime Destiny 2025! Stop by their tables during their autographing hours, 11AM - 2PM and 4PM - 6PM, to chat, get your merch signed, and hang out with them!</p>
          <div class="guess-song-image">
            <img src="images\Anime Destiny 2025 Post Graphics\Anime_Destiny_2025_-_Star_Rail_Panel.png" alt="Work in Progress" />
          </div>
        </section>

      <section id="emaqi" class="program-card" class:glow={currentHash === "#emaqi"}>
          <div class="name-bar"><h4>Emaqi Manga App</h4></div>
          <p><strong>Location:</strong> Pauley Ballroom Booth 2</p>
          <p><strong>Time:</strong> All Day</p>
          <p>Visit an industry booth by Emaqi Manga App, a digital manga store based in Japan! Experience app demos as well as learn more about Emaqi’s manga donation to the Berkeley East Asian Library (opening soon)!</p>
          <div class="guess-song-image">
            <img src="images\exhibition\emaqi.png" alt="Work in Progress" />
          </div>
        </section>

      <section id="bart-anime" class="program-card" class:glow={currentHash === "#bart-anime"}>
          <div class="name-bar"><h4>BART Anime</h4></div>
          <p><strong>Location:</strong> Pauley Ballroom Booth 3</p>
          <p><strong>Time:</strong> All Day</p>
          <p>The BART has Anime mascots?!? Come to the BART Anime booth to pick up freebies as well as see the cutouts of your favorite mascots and the BART train! There will also be exclusive merch sales happening from 10AM - 2PM, so don't miss out!</p>
          <div class="guess-song-image">
            <img src="images\exhibition\bart.png" alt="Work in Progress" />
          </div>
        </section>
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
