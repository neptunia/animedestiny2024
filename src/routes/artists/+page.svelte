<script>
import Footer from '$lib/components/Footer.svelte';
import Navbar from '$lib/components/Navbar.svelte';
import { artists } from './artists.js';
import { fade } from 'svelte/transition';

  // Utility function to determine if the socials field is a URL
  function isUrl(socials) {
    if (Array.isArray(socials)) return false;
    return socials.startsWith('http://') || socials.startsWith('https://') || socials.includes('.co');
  }

  // Helper function to add protocol if missing
  function formatUrl(socials) {
    if (socials.startsWith('http://') || socials.startsWith('https://')) {
      return socials;
    }
    return `https://${socials}`;
  }

  let showOverlayArtistMap = false;

  function openOverlayArtistMap() {
    showOverlayArtistMap = true;
  }

  function closeOverlayArtistMap() {
    showOverlayArtistMap = false;
  }

</script>

<Navbar />

<main>
  <div class="page-title">
    Artist Alley
  </div>
  <div class="artists-info">
    <p style="font-family: 'Montserrat', sans-serif; font-size: 1.5rem; color: #485077; margin-bottom: 1rem;">To Be Announced - Stay Tuned!</p>
    <!--
    <p>Please be mindful of artists' original works and refrain from explicit photography/recording of artists' creations unless you have permission.</p>
    <p>Anime Destiny and Cal Animage Alpha do not support the distribution or showcasing of AI art.</p>
    -->
  </div>

  <!-- Remove this comment once the final artist alley map is complete-->
  <!--
  <div class="content-container">
  <img src="images/AD 2025 Detailed Map.png" class="ADMap" alt="Artist Alley Map" on:click={openOverlayArtistMap} />
    <div style="padding:1rem 0;">
    <a on:click={openOverlayArtistMap}>Click for larger image!</a>
    </div>
    {#if showOverlayArtistMap}
      <div class="overlay-artist-map"  on:click={closeOverlayArtistMap} in:fade={{ duration: 200 }} out:fade={{ duration: 200 }} >
        <button class="close-button-artist-map" on:click={closeOverlayArtistMap}>✕</button>
        <img src="images/AD 2025 Detailed Map.png" on:click|stopPropagation class="image-artist-map" alt="Fullscreen Artist Alley Map" />
      </div>
    {/if}

  </div>
  -->

  <!--
  <div class="artists-grid">
    {#each artists as { name, socials, description, location }}
      <div class="artist-card">
        <div class="name-bar">
          <h2>{name}</h2>
        </div>
        
        {#if socials && isUrl(socials)}
          <a href="{formatUrl(socials)}" target="_blank" rel="noopener noreferrer">{socials}</a>
        {:else if socials !== ""}
          <p>Social Media: {socials}</p>
        {/if}
  
        {#if description}
          <p>{description}</p>
        {/if}
        
        <p class="location">Location: {location}</p>
      </div>
    {/each}
  </div>
  -->
</main>

<style>
  main {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }

  h1 {
    text-align: center;
    margin-bottom: 1.5rem;
  }
  
  .artists-info {
    display: flex;
    flex-wrap: wrap; /* Allows wrapping of items */
    flex-direction: column;
    text-align: center;
    justify-content: center; /* Center the flex items */
    gap: 20px; /* Space between each card */
    max-width: 100rem; /* Set the max width of the grid container */
    width: 100%; /* Ensure the grid spans full width */
    margin: 0 auto; /* Center the grid container horizontally */
    padding-top:2rem;
    padding-left: 1rem;
    padding-right: 1rem;
  }
  .artists-grid {
    display: flex;
    flex-wrap: wrap; /* Allows wrapping of items */
    flex-direction: column;
    justify-content: center; /* Center the flex items */
    gap: 20px; /* Space between each card */
    max-width: 100rem; /* Set the max width of the grid container */
    width: 100%; /* Ensure the grid spans full width */
    margin: 0 auto; /* Center the grid container horizontally */
    padding-top:2rem;
    padding-bottom: 2rem;
    padding-left: 1rem;
    padding-right: 1rem;
  }

  .artist-card {
    background-color: #f9f9f9;
    border: 2px solid #1d3557;
    padding: 0 1rem 1rem 1rem;
    border-radius: 8px;
    transition: box-shadow 0.3s ease, transform 0.3s ease;
    text-align: left;
    max-width: 100rem;
    
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

  .artist-card:hover {
    box-shadow: 0 0 10px 3px rgba(29, 53, 87, 0.5); /* Slight glow */
    transform: translateY(-3px); /* Slight lift */
  }

  .artist-card h2 {
    font-size: 1.25rem;
  }

  .artist-card a {
    display: inline-block;
    margin-bottom: 0.5rem;
    color: #0070f3; /* Link color */
    text-decoration: none;
    font-weight: bold;
    word-break: break-all; /* Ensure long URLs wrap properly */
  }

  .artist-card a:hover {
    color: #0056b3; /* Darker blue on hover */
  }

  .artist-card p {
    margin: 0.25rem 0;
    color: #333;
  }

  .artist-card .location {
    font-style: italic;
    color: #555;
  }

  .ADMap {
    margin: 0 auto;
    max-height: 40rem;
    width: auto;
  }

  .overlay-artist-map {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.8);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
  }

  /* Styling for the close (X) button */
  .close-button-artist-map {
    position: absolute;
    top: 20px;
    right: 20px;
    background: none;
    color: white;
    font-size: 2rem;
    cursor: pointer;
    border: none;
  }

  /* Image styling */
  .image-artist-map {
    max-width: 100vw;
    max-height: 100vh;
    width: auto;
    height: auto;
    border-radius: 8px;
  }

  .content-container {
    text-align: center;
    margin: 2rem 0;
  }
</style>

<Footer />
