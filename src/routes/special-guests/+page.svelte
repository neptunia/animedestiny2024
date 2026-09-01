<script>
  import { guests } from './guests.js';
  import { fade, slide } from 'svelte/transition';
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';

  // Ensure 8 total cards
  const maxGuests = 9;
  const filledGuests = [
    ...guests,
    ...Array.from({ length: maxGuests - guests.length }, () => ({
      name: "Coming Soon...",
      socials: null,
      image: "/images/mystery.png",
      blurb: null,
      comingSoon: true
    }))
  ];

  // Track expanded states for each guest
  let expanded = filledGuests.map(() => false);

  function toggleDescription(index) {
    expanded[index] = !expanded[index];
  }
</script>

<Navbar />

<main>
  <div class="page-title">Special Guests</div>

  <div class="container mx-auto  px-4 py-4">
    <p>We're excited to announce our special guest lineup for Anime Destiny 2026, with some of your favorite industry professionals and VTubers! Click on each image to learn about them.</p>
  </div>
<div  class="container mx-auto px-4 py-12">
<div class="grid grid-cols-1 sm:grid-cols-3 lg:grid-cols-3 gap-6 items-start">
  {#each filledGuests as guest, i (i)}
    <div class="bg-gray-50 rounded-lg shadow flex flex-col">
      <!-- Image area: clickable for real guests, static for coming soon -->
          <div>
            <!-- Clickable image -->
            <!-- Image with overlay -->
            <div 
              class="relative cursor-pointer group"
              on:click={() => toggleDescription(i)}
            >
              <img
                src={guest.image}
                alt={guest.name}
                class="w-full aspect-square object-contain bg-gray-100"
              />

              <!-- Overlay -->
              <div
                class="absolute inset-0 bg-black bg-opacity-40 opacity-0 
                      group-hover:opacity-100 transition flex items-center 
                      justify-center text-white text-lg font-semibold"
              >
                Click to learn more
              </div>
            </div>

            <!-- Name always visible -->
            <p class="text-2xl my-2 font-semibold text-gray-900 text-center">{guest.name}</p>

            <!-- Description only shows when expanded[i] is true -->
            {#if expanded[i]}
              <div transition:slide|local class="bg-gray-50 rounded-b-lg p-3">
              {#if guest.blurb}
                <p class="mt-1 text-sm text-gray-600" style="white-space: pre-line;">{guest.blurb}</p>
              {/if}

              {#if guest.socials}
              <div class="text-center">
                {#if guest.social_type === "instagram"}
                <a
                  class="inline-block mt-3 text-pink-500 hover:text-pink-600"
                  href={guest.socials}
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="Follow on Instagram"
                >
                  <!-- Instagram Flat Icon SVG -->
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 32 32"
                    fill="currentColor"
                    class="w-10 h-10"
                  >
                    <path d="M20.445 5h-8.891A6.559 6.559 0 0 0 5 11.554v8.891A6.559 6.559 0 0 0 11.554 27h8.891a6.56 6.56 0 0 0 6.554-6.555v-8.891A6.557 6.557 0 0 0 20.445 5zm4.342 15.445a4.343 4.343 0 0 1-4.342 4.342h-8.891a4.341 4.341 0 0 1-4.341-4.342v-8.891a4.34 4.34 0 0 1 4.341-4.341h8.891a4.342 4.342 0 0 1 4.341 4.341l.001 8.891z"/><path d="M16 10.312c-3.138 0-5.688 2.551-5.688 5.688s2.551 5.688 5.688 5.688 5.688-2.551 5.688-5.688-2.55-5.688-5.688-5.688zm0 9.163a3.475 3.475 0 1 1-.001-6.95 3.475 3.475 0 0 1 .001 6.95zM21.7 8.991a1.363 1.363 0 1 1-1.364 1.364c0-.752.51-1.364 1.364-1.364z"/>
                  </svg>
                </a>
                {/if}
                {#if guest.social_type === 'youtube'}
                <a
                  class="inline-block mt-3 text-red-500 hover:text-red-600"
                  href={guest.socials}
                  target="_blank"
                  rel="noopener noreferrer"
                  aria-label="Subscribe on YouTube"
                >
                <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="w-10 h-10" viewBox="0 0 16 15.5">
                  <path d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105-.009.104c-.05.572-.124 1.14-.235 1.558a2.01 2.01 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006-.087-.004-.171-.007-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.01 2.01 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31 31 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103.003-.052.008-.104.022-.26.01-.104c.048-.519.119-1.023.22-1.402a2.01 2.01 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007.172-.006.086-.003.171-.007A100 100 0 0 1 7.858 2zM6.4 5.209v4.818l4.157-2.408z"/>
                </svg>
                </a>
                {/if}
                </div>
              {/if}
              </div>
            {/if}
          </div>
      </div>

          
  {/each}
</div>

</div> <!-- close container wrapper (matches your existing file) -->
</main>

<Footer />