<script>
  import { fade } from 'svelte/transition'; // Import fade transition
  let isOpen = false;
  let isHomeOpen = false;
  let isProgrammingOpen = false;
  let ticketLink = 'https://buy.stripe.com/8x28wQ9Qcb1ccWl5ebbAs01';
  let discord = 'https://discord.com/invite/Xp4MUjG';
  let instagram = 'https://www.instagram.com/calanimagealpha/';

  // Function to show the dropdown on hover
  function openHomeDropdown() {
    isHomeOpen = true;
  }

  // Function to close the dropdown when mouse leaves
  function closeHomeDropdown() {
    isHomeOpen = false;
  }
  const toggleMenu = () => {
    isOpen = !isOpen;
  };

  const closeMenu = () => {
    isOpen = false;
  };

  function openProgrammingDropdown() {
    isProgrammingOpen = true;
  }

  function closeProgrammingDropdown() {
    isProgrammingOpen = false;
  }
</script>

<nav class="navbar">
  <div class="logo">
    <a href="/" in:fade={{ duration: 500 }} style="font-family: 'Roboto', sans-serif; font-size: 1.8rem;">Anime Destiny</a>
  </div>

  <!-- Desktop Menu -->
  <div class="menu-items desktop-only">
    <!-- Home Dropdown -->
    <div class="dropdown" 
        role="button"
        aria-haspopup="true"
        aria-expanded={isHomeOpen}
        tabindex="0"
        on:mouseover={openHomeDropdown} 
        on:mouseleave={closeHomeDropdown}
        on:focus={openHomeDropdown} 
        on:blur={closeHomeDropdown}>

      <!-- Home link with dropdown indicator -->
      <a href="#" class="dropdown-toggle" aria-label="Home menu">AD Info ▾</a>

      <!-- Dropdown Menu -->
      {#if isHomeOpen}
        <div class="dropdown-menu" in:fade={{ duration: 200 }} out:fade={{ duration: 300 }}>
          <a href="/">Homepage</a>
          <a href="/about">About AD</a>
          <a href="/artists">Artist Alley</a>
          <a href="/#map-schedule">Schedule and Map</a>
          <a href="/parking">Parking</a>
          <a href="/sponsors">Sponsors</a>
        </div>
      {/if}
    </div>

    <!-- Programming Dropdown -->
    <div class="dropdown"
       role="button"
       aria-haspopup="true"
       aria-expanded={isProgrammingOpen}
       tabindex="0"
       on:mouseover={openProgrammingDropdown}
       on:mouseleave={closeProgrammingDropdown}
       on:focus={openProgrammingDropdown}
       on:blur={closeProgrammingDropdown}>

    <!-- Programming link with dropdown indicator -->
    <a href="#" class="dropdown-toggle" aria-label="Programming menu">Programming ▾</a>


    <!-- TODO make programming page and link them to sections in programming -->
     <!-- Add relevant panels, performances, and workshops here -->
    <!-- Dropdown Menu -->
    {#if isProgrammingOpen}
  <div class="dropdown-menu" in:fade={{ duration: 200 }} out:fade={{ duration: 300 }}>
    <div class="sub-links">To Be Announced - Stay Tuned!</div>

    <!-- Category: 3rd Floor - Stephens Hall -->
    <!--
    <div class="category">Pauley Ballroom (3rd Floor)</div>
    <div class="sub-links">
      <a href="/artists">Artist Alley</a>
      <a href="/special-guests">Special Guests</a>
    </div>
    -->

    <!--
    <div class="category">Stephens Hall (3rd Floor)</div>
    -->
    <div class="sub-links">
      <!-- Events (Chronological)-->
      <!-- Perhaps add start and end time for artist alley?-->
      <!--
      <a href="/programming#panel-guess-song">Guess The Song: Anime Edition</a>
      <a href="/programming#event-nene-qna">Q&A with Nene Amano</a>
      <a href="/programming#event-shipgirls">Shipgirls and Jetgirl VTubers? : Welcome to VFleet Project</a>
      <a href="/programming#event-jpop-kpop">J-Pop/K-Pop Random Play Dance</a>
      <a href="/programming#event-himeko-firefly">All Aboard the Astral Express with Himeko and Firefly!</a>
      <a href="/programming#event-nikkei-choral-performance">Nikkei Choral Ensemble</a>
      <a href="/programming#event-genshin-club">Genshin at Berkeley Event</a>
      -->
    </div>

    <!-- Category: 5th Floor - Tilden Room -->
    <!--
    <div class="category">Tilden Room (5th Floor)</div>
    -->
    <div class="sub-links">
      <!-- Events (Chronological)-->
      <!--
      <a href="/programming#panel-issei-band">Issei Band: Student Anime Band & Opening Ceremony</a>
      <a href="/programming#panel-cosplay-competition-101">Cosplay Contest 101 Panel & Contest Pre-Judging</a>
      <a href="/programming#event-cosplay-comp">Cosplay Contest</a>
      <a href="/programming#event-otaku-ongaku">Otaku Ongaku: Nerd Music LIVE!</a>
      <a href="/programming#event-wotagei">Introduction to Wotagei 101</a>
      <a href="/programming#event-intermission">The Intermission Orchestra</a>
      <a href="/programming#event-virtual-bears">Virtual Bears: VTuber Mini Concert</a>
      -->
    </div>
  </div>
{/if}

  </div>
  <a href="/cosplay">Cosplay</a>
  <a href="/exhibition">Exhibitions</a>
  <a href="/rules">Rules</a>
  <a href="/special-guests">Special Guests</a>
    <!-- Buy a Ticket -->
    <!-- <a
      href={ticketLink}
      class="ml-4 inline-block rounded-full bg-[#3F6CC9] px-5 py-2 -my-1 text-xs font-bold tracking-wide text-white uppercase font-['Montserrat'] shadow-md hover:bg-[#2F4898] transition-colors duration-200"
    >
      Purchase Tickets
    </a> -->

    <!-- Discord and Instagram 
    <a href={discord} target="_blank" rel="noopener noreferrer" in:fade={{ duration: 500 }}>
      <img src="icons/discord.svg" alt="Discord" class="icon"/>
    </a>
    <a href={instagram} target="_blank" rel="noopener noreferrer" in:fade={{ duration: 500 }}>
      <img src="icons/instagram.svg" alt="Instagram" class="icon"/>
    </a>
    -->
  </div>
  <!-- Mobile Menu Trigger -->
  <div class="hamburger mobile-only" on:click={toggleMenu}>
    <div class="bar"></div>
    <div class="bar"></div>
    <div class="bar"></div>
  </div>

  <!-- Mobile Menu -->
  <div class="mobile-menu {isOpen ? 'show' : ''}">
    <div class="mobile-logo">
      <a href="/" on:click={closeMenu} in:fade={{ duration: 500 }}>Anime Destiny</a>
    </div>
    <div class="close-btn" on:click={closeMenu}>✖</div>

    <div class="menu-content">
      <!-- TODO Add more pages (e.g. panels, workshops, etc.)
          - cosplay contest
          - gaming area
          - move artists here? -->
          <!-- Add programming items later -->

      <!-- Mobile Menu -->
      <a href="/" on:click={closeMenu} in:fade={{ duration: 500 }}>Homepage</a>
      <a href="/about" on:click={closeMenu} in:fade={{ duration: 500 }}>About AD</a>
      <a href="/artists" on:click={closeMenu} in:fade={{ duration: 500 }}>Artist Alley</a>
      <a href="/special-guests" on:click={closeMenu} in:fade={{ duration: 500 }}>Special Guests</a>
      <a href="/programming" on:click={closeMenu} in:fade={{ duration: 500 }}>Programming</a>
      <!--<a href="/cosplay-contest" on:click={closeMenu} in:fade={{ duration: 500 }}>Cosplay Contest</a>-->
      <a href="/rules">Rules</a>
      <a href="/sponsors">Sponsors</a>
      
      <!-- Discord and Instagram Icons 
      <a href={discord} target="_blank" rel="noopener noreferrer" in:fade={{ duration: 500 }}>
         Join our Discord!
      </a>
      <a href={instagram} target="_blank" rel="noopener noreferrer" in:fade={{ duration: 500 }}>
        Follow our Instagram!
      </a>
      -->


    </div>
          <a
      href={ticketLink}
      class="block w-full bg-[#3F6CC9] py-7 -my-[6rem] text-center text-4xl font-bold uppercase tracking-wide text-white font-['Montserrat'] hover:bg-[#2F4898] transition-colors duration-200"
    >
      Buy Tickets
    </a>
  </div>
</nav>

<style>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    background-color: black;
    color: white;
    position: relative;
    z-index: 10;
  }

  .logo a {
    font-size: 1.5rem;
    color: white;
    text-decoration: none;
  }

  .menu-items a, .menu-content a {
    margin-left: 1.5rem;
    color: white;
    text-decoration: none;
    font-size: 1rem;
    transition: color 0.3s ease;
  }


  /* Hover effect for yellow highlight */
  .menu-items a:hover, .menu-content a:hover {
    color: #fed893;
  }

  .desktop-only {
    display: none;
  }

  .mobile-only {
    display: flex;
    flex-direction: column;
    justify-content: center;
    cursor: pointer;
  }

  .dropdown-menu {
    display: flex;
    flex-direction: column;
    background-color: rgb(49, 49, 49);
    position: absolute;
    padding: 0.3rem 2rem 0.3rem 0.1rem;
    margin-top: 0.5rem;
    /*border: 1px solid white;
    border-radius: 5px;*/
  }

  .dropdown-menu a {
    color: white;
    padding: 0.5rem;
    text-decoration: none;
    
  }

  .dropdown-menu a:hover {
    color: #fed893;
  }

  .dropdown-toggle {
    cursor: pointer;
    position: relative;
    padding-bottom:1.3rem;
  }

  .bar {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 3px 0;
  }

  /* Discord and Instagram Icons */
  .icon {
    width: 24px;
    height: 24px;
  }

  /* Mobile Menu Styles */
  .mobile-menu {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #101030;
    opacity: 0;
    visibility: hidden;
    transform: translateY(-100%);
    transition: opacity 0.5s ease, transform 0.5s ease, visibility 0.5s ease;
    z-index: 20;
  }

  .mobile-menu.show {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
  }

  .mobile-logo {
    position: absolute;
    top: 1rem;
    left: 1rem;
  }

  .mobile-logo a {
    font-family: 'Roboto', sans-serif;
    font-size: 1.8rem;
    color: white;
    text-decoration: none;
  }

  .menu-content {
    display: flex;
    flex-direction: column;
    /*justify-content: center;*/
    /*align-items: center;*/
    padding-left: 2rem;
    padding-top: 3.5rem;
    height: 100%;
    font-family: 'Segoe UI', sans-serif;
    font-weight:200;
  }

  .menu-content a {
    font-size: 1.8rem;
    margin: 1rem 0;
  }

  .close-btn {
    position: absolute;
    top: 0.7rem;
    right: 1rem;
    font-size: 2rem;
    color: white;
    cursor: pointer;
  }

  /* Sub-links under categories */
  .sub-links {
    padding-left: 20px; /* Indent the sub-links */
  }

  .main-links {
    padding-top:10px;
    margin-left: 5px!important; /* Indent the sub-links */
  }


  .sub-links a {
    display: block;
    margin: 5px 0;
  }

  /* Category Styling */
  .category {
    font-weight: bold;
    color: grey;
    margin-top: 10px;
    padding-left: 0.8em;
    cursor: default;
  
  }



  /* Desktop Menu (Media Query) */
  @media(min-width: 768px) {
    .desktop-only {
      display: flex;
    }

    .mobile-only {
      display: none;
    }
  }
</style>
