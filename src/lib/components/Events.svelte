<script>
    let currentIndex = 0;
  
    const events = [
      {
        title: "Cosplay Contest",
        description: "Show off your amazing costumes and compete for prizes in various categories!",
        image: "images/cosplay/3.png",
        link: "/cosplay-contest",
      },
      {
        title: "Genshin at Berkeley Club Event",
        description: "Join fellow Hoyoverse fans for fun activities and prizes.",
        image: "images/cosplay/1.png",
        link: "/programming#event-genshin-club",
      },
      {
        title: "Intermission Orchestra Performance",
        description: "Live music from anime, video games, and more by Berkeley's orchestra.",
        image: "images/tio_pic.png",
        link: "/programming#event-intermission-orchestra",
      },
      {
        title: "Nikkei Choral Ensemble Performance",
        description: "A beautiful acapella set of J-pop, anime songs, and more.",
        image: "images/nikkei_pic.png",
        link: "/programming#event-nikkei-choral-performance",
      },
    ];
  
    function nextSlide() {
      currentIndex = (currentIndex + 1) % events.length;
    }
  
    function previousSlide() {
      currentIndex = (currentIndex - 1 + events.length) % events.length;
    }
  </script>
  
  <main class="slideshow">
    <div class="slideshow-container">
      {#each events as event, index}
        {#if index === currentIndex}
          <a href={event.link} class="slide" style="opacity: 1;">
            <img src={event.image} alt="{event.title}" class="slide-image" />
            <div class="slide-overlay">
              <h3>{event.title}</h3>
              <p>{event.description}</p>
            </div>
          </a>
        {:else}
          <a href={event.link} class="slide" style="opacity: 0; pointer-events: none;">
            <img src={event.image} alt="{event.title}" class="slide-image" />
            <div class="slide-overlay">
              <h3>{event.title}</h3>
              <p>{event.description}</p>
            </div>
          </a>
        {/if}
      {/each}
      <button class="prev" on:click={previousSlide}>&#10094;</button>
      <button class="next" on:click={nextSlide}>&#10095;</button>
    </div>
  </main>
  
  <style>
    .slideshow {
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: #ffffff;
      padding: 2rem;
    }
  
    .slideshow-container {
      position: relative;
      width: 100%;
      max-width: 800px;
      height: 400px; /* Fixed height to prevent content shifting */
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
      background: #ffffff;
    }
  
    .slide {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      text-decoration: none;
      color: inherit;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      transition: opacity 0.5s ease;
    }
  
    .slide-image {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }
  
    .slide-overlay {
      position: absolute;
      bottom: 0;
      background: rgba(0, 0, 0, 0.5);
      color: white;
      width: 100%;
      padding: 1rem;
      text-align: center;
      font-family: 'Montserrat', sans-serif;
    }
  
    .slide-overlay h3 {
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
    }
  
    .slide-overlay p {
      font-size: 1rem;
      margin: 0;
    }
  
    .prev, .next {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background-color: rgba(0, 0, 0, 0.5);
      color: white;
      border: none;
      padding: 0.5rem;
      border-radius: 50%;
      cursor: pointer;
      transition: background-color 0.3s ease;
      font-size: 1.5rem;
    }
  
    .prev {
      left: 10px;
    }
  
    .next {
      right: 10px;
    }
  
    .prev:hover, .next:hover {
      background-color: rgba(0, 0, 0, 0.7);
    }
  
    @media (max-width: 768px) {
      .slideshow-container {
        height: 250px; /* Adjust height for mobile */
      }
  
      .slide-overlay h3 {
        font-size: 1.2rem;
      }
  
      .slide-overlay p {
        font-size: 0.9rem;
      }
    }
  </style>
  