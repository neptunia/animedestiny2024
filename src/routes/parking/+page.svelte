<script>
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>
  
<Navbar />

<main class="confirmation-page">
  <div class="page-title">
    Parking
  </div>
  <section id="map-schedule" class="parking-info">
    <div>
      <p>
        Street parking may be available around the Berkeley campus. You may also park at the following garages and lots:
      </p>
      <ul>
        <li>Lower Sproul Lot</li>
        <li>Recreational Sports Facility (RSF) Garage</li>
        <li>Telegraph-Channing Garage</li>
        <li>Bancroft Structure</li>
        <li>Upper Hearst Structure</li>
        <li>Stadium Parking Garage</li>
      </ul>
      <p>
        For more information, consult: 
        <a href="https://berkeleyca.gov/city-services/parking/parking-garages-and-lots" target="_blank" rel="noopener noreferrer">
          Berkeley Parking Garages and Lots
        </a> and 
        <a href="https://pt.berkeley.edu/sites/default/files/2018_ucb_map_051018_1.pdf" target="_blank" rel="noopener noreferrer">
          Berkeley Parking Map (PDF)
        </a>.
      </p>
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
    background-color: #f0f4f8;
  }
  
  .confirmation-page {
    padding: 0;
    margin: 0; 
  }
  
  
  .parking-info {
    padding: 2rem;
    max-width: 800px;
    margin: 0 auto;
    text-align: left;
    font-family: 'Montserrat', sans-serif;
    color: #485077;
  }
  
  .parking-info p {
    font-size: 1.1rem;
    margin-bottom: 1rem;
  }
  
  .parking-info ul {
    list-style-type: disc;
    margin-left: 1.5rem;
    margin-bottom: 1rem;
  }
  
  .parking-info a {
    color: #485077;
    text-decoration: underline;
    transition: color 0.3s ease;
  }
  
  .parking-info a:hover {
    color: #fed893;
  }

  /* Mobile Styling */
  @media (max-width: 768px) {
    .page-title {
      font-size: 2rem;
      height: 8rem;
    }

    .parking-info p,
    .parking-info ul {
      font-size: 1rem;
    }
  }
</style>
