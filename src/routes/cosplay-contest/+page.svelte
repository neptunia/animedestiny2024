<script>
  import Footer from '$lib/components/Footer.svelte';
  import Navbar from '$lib/components/Navbar.svelte';
  import { onDestroy } from 'svelte';
  import { fade } from 'svelte/transition';
  const judges = [
    
    {
      name: "Astro (astros_here)",
      description: "_______________",
      intro: "Meet Astro ( astros_here ) a 55+ Award winning master level competitive cosplayer from central California! They specialize in sewing and needlework but dabbles is alot of different mediums and materials! Astro knows a plethora of techniques and skills! They have competed and judges all over the United states and have been published in magazines before! They have been cosplaying for 8 years and have made well over 30+ unique costumes! Astro is also a chronically ill/disabled and queer cosplayer who wants to carve out a space for everyone within the cosplay community! Come meet and talk shop with Astro! They are always willing to give advice on cosplay, build books and more!",
      socialLink: "https://www.instagram.com/astros_here/",
      socialName: "@astros_here",
      imageUrl: "images/AnimeDestiny-2025CosplayGuestAstro.jpg"
    },
    {
      name: "Elee (theacalix)",
      description: "_______________",
      intro: "Theacalix is a masters level cosplayer with 13 years of experience. They specialize in sewing craftsmanship builds across a variety of media with a specialty in original design. Thea loves to chat about cosplay, craftsmanship, and fandom so come say hi!",
      socialLink: "https://www.instagram.com/theacalix/",
      socialName: "@theacalix",
      imageUrl: "images/AnimeDestiny-2025CosplayGuestThecalix.jpg"
    },
    {
      name: "Max (Deadgoatcos)",
      description: "_______________",
      intro: "Deadgoatcos is excited for her first guesting experience. With her 7 years of cosplaying and certificate of costume design she is so happy to share her knowledge and expertise with the con goers. Thank you Anime Destiny for allowing me this opportunity. See everyone at con!!",
      socialLink: "https://www.instagram.com/deadgoatcos/",
      socialName: "@deadgoatcos",
      imageUrl: "images/AnimeDestiny-2025CosplayGuestDeadgoatcos.jpg"
    }
  ];


  let currentImageIndex = 0;
  const images = [
    '/images/cosplay/1.png',
    '/images/cosplay/2.png',
    '/images/cosplay/3.png',
    '/images/cosplay/4.png', 
    '/images/cosplay/5.png' 
  ];

  let interval = null;

  // Start the slideshow
  const startSlideshow = () => {
    interval = setInterval(() => {
      nextImage();
    }, 7000);
  };

  const stopSlideshow = () => {
    clearInterval(interval);
  };

  // Move to the next image
  const nextImage = () => {
    currentImageIndex = (currentImageIndex + 1) % images.length;
  };

  // Move to the previous image
  const prevImage = () => {
    currentImageIndex = (currentImageIndex - 1 + images.length) % images.length;
  };

  // Jump to a specific image
  const jumpToImage = (index) => {
    currentImageIndex = index;
    stopSlideshow();
    startSlideshow(); // Restart the slideshow after manual navigation
  };

  // Cleanup the interval on component destroy
  onDestroy(() => {
    clearInterval(interval);
  });

  // Start the slideshow initially
  startSlideshow();


  </script>
  
  <Navbar />
  
  <main>
    <div class="page-title">
      Cosplay Contest
    </div>
    <div class="page-body">

      <section id="workshop-cosplay-contest">
        <div class="spacer"></div>
        <p>
          We will be holding our annual AD cosplay contest this year in <strong>Tilden Room</strong> from <strong>12:00 PM - 1:00 PM</strong>.
        </p>
        <p>
          Join Berkeley’s cosplayers for a fun and welcoming event! Show off your cosplaying skills or just enjoy watching the amazing talent at Anime Destiny.
          Anyone who has a costume and is interested is welcome to join! Whether you're a seasoned cosplayer or it's your first time, we'd love to see you there!
          Sign up here: <a href="https://forms.gle/hXUxzeVHSgghcyyh8" target="_blank" class="section-link">Cosplay Sign-Up Form</a>  
        </p>
        <div class="spacer"></div>
        <p>
          Prizes will be awarded to the top three cosplays, as determined by our judging panel. The prizes are as follows:
        </p>
        <ul class="prizes-list">
          <li><strong>Best in Craftsmanship: </strong> Anime Destiny Lifetime Pass + Anime Destiny Merchandise + $50</li>
          <li><strong>Best in Performance: </strong> Anime Destiny Lifetime Pass + Anime Destiny Merchandise + $50</li>
          <li><strong>2nd Place Overall:</strong> Anime Destiny Merchandise + $25</li>
          <li><strong>3rd Place Overall: </strong> $25 </li>
        </ul>

        <br>

        <div class="centered">Meet our judges:</div>

        <div class="container">
          
          {#each judges as { name, description, intro, socialLink, socialName, imageUrl }}
            <div class="card">
              <img src={imageUrl} alt={name} class="card-image"/>
              <div class="card-content">
                <h2 class="card-name">{name}</h2>
                <p class="card-desc">{description}</p>
                <p class="card-intro">{intro}</p>
                {#if socialLink}
                  Instagram: <a href={socialLink} target="_blank" rel="noopener noreferrer">{socialName}</a>
                {/if}
              </div>
            </div>
          {/each}
        </div>
        <div class="spacer"></div>
        <div class="centered">Photo Gallery</div>

        <div class="spacer"></div>

        <div class="gallery">
          <!-- Arrow Buttons -->
          <button class="arrow left" on:click={prevImage}>‹</button>
          <button class="arrow right" on:click={nextImage}>›</button>
        
          <!-- Image Display with Fade Transition (overlaying images) -->
          <div class="image-container">
            {#each images as image, index}
              <img 
                src={image} 
                alt="Cosplay Image" 
                class="gallery-image" 
                in:fade={{ duration: 500 }} 
                out:fade={{ duration: 500 }} 
                class:active={currentImageIndex === index} 
              />
            {/each}
          </div>
        
          <!-- Image Indicators (Circles) -->
          <div class="indicators">
            {#each images as _, index}
              <span 
                class:active={currentImageIndex === index} 
                class="dot" 
                on:click={() => jumpToImage(index)}></span>
            {/each}
          </div>
        </div>

        <div class="spacer"></div>

        <div class="bottom-text">
          What are you waiting for? <a href="https://forms.gle/hXUxzeVHSgghcyyh8" target="_blank" class="section-link">Sign Up Now!</a>  

        </div>
        
          <!-- ADD MORE CONTENT HERE!!! ALSO PICS!!!-->
          
      </section>

    </div>
    
  </main>
  
  <style>
    main {
      flex-grow: 1;
      display: flex;
      flex-direction: column;
    }

    .bottom-text {
      text-align: center;
      font-size: 1.5rem;
    }
    .card-name {
      font-size: 1.8rem;
      padding-bottom: 1rem;
    }
    .prizes-list {
      padding: 0.5rem 0rem 0.5rem 2rem;
      
    }
    .prizes-list li {
      margin: 10px 0;
    }
    .centered {
      text-align:center;
      font-size: 2rem;
      font-weight:600;
    }
    .spacer {
      padding-top:2rem;

    }
    .card-desc {
      font-style: italic;
      color: #555;
      margin-top: -0.8rem;
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

      /* Container for the three side-by-side cards */
    .container {
      display: flex;
      justify-content: center; /* Evenly space the cards */
      gap: 1.5rem; /* Space between the cards */
      flex-wrap: wrap; /* Allow wrapping on smaller screens */
      padding: 20px;
    }

    /* Individual card styling */
    .card {
      background-color: #f9f9f9;
      border: 1px solid #ddd;
      border-radius: 8px;
      width: 30%; /* Make sure each card takes up 30% of the container's width */
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 20px;
    }

    /* Image styling */
    .card-image {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      object-fit: cover;
      margin-bottom: 15px;
    }

    /* Card content styling */
    .card-content {
      text-align: center;
    }

      /* Social link styling */
    .card-content a {
      color: #485077;
      text-decoration: none;
      font-weight: bold;
      transition: color 0.3s ease;
    }

    .card-content a:hover {
      color: #fed893;
    }

    /* Responsive adjustments for smaller screens */
    @media (max-width: 900px) {
      .card {
        width: 45%; /* Adjust width for smaller screens */
      }
    }

    @media (max-width: 600px) {
      /* Stack the cards vertically on smaller screens */
      .container {
        flex-direction: column; /* Change direction to column */
        align-items: center; /* Center the cards */
      }

      .card {
        width: 100%; /* Full width for each card */
        margin-bottom: 20px; /* Add space between cards */
      }
    }

    /* Gallery container */
    .gallery {
      position: relative;
      width: 100%;
      height: 400px; /* Set the height of the gallery */
      display: flex;
      justify-content: center;
      align-items: center;
      overflow: hidden;
    }

    /* Arrow buttons */
    .arrow {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0, 0, 0, 0.5);
      color: white;
      border: none;
      padding: 10px;
      cursor: pointer;
      font-size: 2rem;
      z-index: 1;
      transition: background 0.3s ease;
    }

    .arrow:hover {
      background: rgba(0, 0, 0, 0.8);
    }

    .arrow.left {
      left: 50px;
    }

    .arrow.right {
      right: 50px;
    }

    /* Image container for overlaying images */
    .image-container {
      position: relative;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    /* Image styling */
    .gallery-image {
      position: absolute;
      max-width: 100%;
      max-height: 100%;
      object-fit: cover;
      opacity: 0;
      transition: opacity 0.5s ease-in-out;
    }

    .gallery-image.active {
      opacity: 1;
    }

    /* Indicators (circles) */
    .indicators {
      position: absolute;
      bottom: 10px;
      display: flex;
      justify-content: center;
      gap: 10px;
    }

    .dot {
      height: 10px;
      width: 10px;
      background-color: rgba(200, 200, 200, 0.5);
      border-radius: 50%;
      display: inline-block;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .dot:hover {
      background-color: rgba(255, 255, 255, 1);
      border: 1px solid #555;
    }

    .dot.active {
      background-color: rgba(255, 255, 255, 1);
      border: 1px solid #555;
    }
    /* Mobile Styles */
    @media (max-width: 768px) {
      .gallery {
        height: 300px; /* Adjust height for mobile screens */
      }

      .dot {
        height: 15px;  /* Increase dot size */
        width: 15px;
      }

      .indicators {
        bottom: 20px; /* Add more space at the bottom for mobile */
      }

      .arrow {
        font-size: 1.5rem; /* Decrease arrow size on mobile */
      }

      .arrow.left {
        left: 5px;
      }

      .arrow.right {
        right: 5px;
      }
    }
  </style>
  
  <Footer/>
