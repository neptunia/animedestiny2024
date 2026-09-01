<script>
  import Footer from '$lib/components/Footer.svelte';
  import Navbar from '$lib/components/Navbar.svelte';
  </script>
  
  <Navbar />
  
  <main>
    <div class="page-title">
      About Us
    </div>
    <div class="page-body">

      <p><b>Anime Destiny</b> is Berkeley's annual anime convention hosted by <b>Cal Animage Alpha</b>, a non-profit student organization founded at UC Berkeley and thriving since 1989. </p>

      <p><b>Cal Animage Alpha</b> is the first anime club of the Cal Animage network, a group of anime clubs that has expanded to universities across the country. Focused on all things anime, manga, and games, our club founders have gone on to create Crunchyroll and Anime Expo, among many other amazing anime-related events and organizations. Here at Cal Animage Alpha, we aim to foster a supportive and welcoming environment where all types of people can gather and meet like-minded individuals. </p>
        
      <p>To this end, we created <b>Anime Destiny</b>. At this annual one-day convention, we invite artists, panelists, guests, speakers, performers, industry professionals, and many more types of people involved in the anime industry to come together and create an amazing experience for the public. Anime Destiny is open to everyone! Especially those who enjoy all things “animage” (anime, manga, and games) or want to learn more about it. </p>
      <p>  
        We hope you have an amazing time at Anime Destiny this year and thank you for supporting Cal Animage Alpha!
      </p>

      <a href="https://cal.moe/about" class="section-link">Learn more about Cal Animage Alpha</a>
      <br/><br/>

      <!-- Remove once new cal animage alpha logo is added-->
      <!-- <img src="images/animage.jpg" alt="Work in Progress" style="width: 80%; height: auto;margin:auto;" /> -->

    </div>
    
  </main>
  
  <style>
    main {
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }
    
    .page-body {
      
      padding: 2rem;
      width: 100%;
      max-width: 100rem;
      margin: auto;
    }
    p {
      margin-bottom: 1rem;
    }

    .section-link {
      color: #485077;
      text-decoration: none;
      font-weight: bold;
      font-size: 1.1rem;
      border-bottom: 2px solid #485077; /* Underline links */
      padding-bottom: 0.2rem;
      line-height:4rem;
      padding-top: 2rem;
      transition: color 0.3s ease, border-bottom-color 0.3s ease;
    }

    .section-link:hover {
      color: #fed893; /* Yellow on hover */
      border-bottom-color: #fed893;
      
    }
  </style>
  
  <Footer/>