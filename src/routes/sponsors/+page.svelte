<script>
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<Navbar />

<main class="confirmation-page">
  <div class="page-title">
    Sponsors and Supporters
  </div>
  <section>
    <div class="page-body">

      <h1 class="text-4xl mb-8 subhead1">Sponsors</h1>
      <p class="my-8">Anime Destiny would not be possible without the support of our sponsors and supporters, thank you so much for helping make Anime Destiny possible!</p>

      <p>A big thank you to Glacia, a local community artist who created the art for the official Anime Destiny flyer this year! 
        Drawing from the “Fantasy” theme of this year’s event, Glacia brought our mascots, Cal and Ani, to life. 
        Please check out Glacia’s table at the Artist Alley as well as support their socials through their handle @glaciavt! </p>

        <img src="/images/mascots2026.png" alt="mascots" class="mx-auto w-full max-w-[80em] h-auto"/>
        <!--eventually make this two seperate images-->
      

    <!--
      <h1 class="text-4xl mb-8 subhead1">Sponsors</h1>
      <img src="/images/Anime Destiny 2025 Post Graphics/Anime_Destiny_2025_-_Sponsors.png" alt="Our sponsors VFleet Project and pixiv" class="mx-auto w-full max-w-[40em] h-auto" />

      <p class="my-8">Anime Destiny 2025 would not be possible without our incredible sponsors pixiv and VFleet Project. 
        We are extremely grateful to them for their support of Anime Destiny 2025 and encourage all attendees to visit 
        their respective booths at our convention (see the map!) as well as checking out their websites: <a href="https://www.pixiv.net/en/" class="link">https://www.pixiv.net/en/</a> and <a href="https://vfleetproject.com/" class="link">https://vfleetproject.com/</a>.
      </p>

      <div class="mb-10">
        <h2 class="text-3xl mb-6"><a href="https://vfleetproject.com/" class="hlink">VFleet Project</a></h2>
        <p>VFleet Project is a virtual entertainment company sailing the virtual seas with the goal of supporting museum ship and aerospace museums around the world! Their mission is to develop and empower creators by offering support to be their best, creative selves in hopes that they will garner support for the ships and aircraft we love. VFleet seeks to raise awareness and support for the nonprofit foundations that are charged with the preservation and restoration of ship museums and aircraft.</p>
        <h2 class="text-3xl mb-6 mt-10"><a href="https://pixiv.net/en/" class="hlink">Pixiv</a></h2>
        <p>Pixiv is a community that makes it easy for illustrators and illustration enthusiasts to communicate with each other through their content, and which allows users to post their own illustrations. The illustrations that you post and bookmark form your profile, and users communicate with each other, with the content of their profiles at the center of their discussions.</p>
      
      </div>

      <hr class="my-6 border-t border-gray-400" />

      <h1 class="text-4xl mb-8 subhead1">Special Thanks</h1>

      <img src="/images/Anime Destiny 2025 Post Graphics/Anime_Destiny_2025_Official_Flyer.png" alt="official flyer" class="mx-auto w-full max-w-[30em] h-auto" />

      <div class="my-10">
        <p>Thank you to an incredible artist from our community Komun Horangi (<a class="link" href="https://x.com/komunhorangi">@komunhorangi</a>) for their help in creating the amazing art for this flyer! 
          They will be participating in Anime Destiny 2025's Artist Alley, so we encourage all attendees to check them out!</p>
      </div>
    -->
      
    </div>
  </section>
</main>

<Footer />

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@700&family=Montserrat:wght@400&display=swap');

  main {
    flex-grow: 1;
    display: flex;
    flex-direction: column;
  }

  .confirmation-page {
    padding: 0;
    margin: 0;
  }

  .subhead1 {
    color: #485077;
    font-weight: 600;
  }
  .page-body {
      
      padding: 1rem;
      width: 100%;
      max-width: 100rem;
      margin: auto;

    }

  .link {
    border-bottom: 1px solid #485077;

  }

  .hlink {
    font-weight:400;
    border-bottom: 2px solid #485077;

  }

</style>
