<script>
  import Navbar from '$lib/components/Navbar.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<Navbar />

<main class="confirmation-page">
  <div class="page-title">
    Convention Rules
  </div>
  <!-- Rules Section -->
  <section id="rules">
    <div class="rules-content">
      <h2>Rules</h2>
      <p>
        Please review these rules to ensure a safe and enjoyable experience at Anime Destiny 2025:
      </p>

      <h3>I. Alcohol and Drugs Policy:</h3>
      <p>
        No alcohol or drugs, including tobacco and other substances, are permitted at the event. Any found will be confiscated, and repercussions will follow.
      </p>

      <h3>II. Code of Conduct:</h3>
      <p>
        Respect others' privacy and personal space. Help those who need assistance. If you see anything suspicious, report it to event staff immediately.
      </p>

      <h3>III. Badges:</h3>
      <p>
        Attendees must wear their badge at all times and be prepared to show identification when entering the event or any program.
      </p>

      <h3>IV. Prohibited Actions and Activities:</h3>
      <ul>
        <li>Failure to be appropriately clothed</li>
        <li>Harassment, lewd behavior, or discrimination</li>
        <li>Unauthorized business transactions</li>
        <li>Skateboarding, soliciting, alcohol consumption, and more (see master doc)</li>
      </ul>

      <h3>V. Prohibited Items:</h3>
      <ul>
        <li>Illegal substances, drugs, weapons (see prop policy)</li>
        <li>Non-service animals, oversized backpacks, flammable items</li>
        <li>Signs, stickers, graffiti</li>
        <li>And more (see master doc)</li>
      </ul>

      <h3>VI. Cosplay Guidelines:</h3>
      <p>
        Shoes must be worn at all times. Costumes should not be excessively revealing or impede traffic. No law enforcement or military uniforms allowed. See the prop/weapon policy for rules on cosplay weapons.
      </p>

      <h3>VII. COVID-19 Statement:</h3>
      <p>
        By attending, you assume all risks associated with potential exposure to COVID-19. Review the latest CDC guidelines before attending.
      </p>

      <h3>VIII. Prop/Weapon Policy:</h3>
      <p>
        No real or dangerous weapons are allowed. Prop weapons must be inspected at the front desk before being brought inside.
      </p>

      <p>
        For the complete list of rules, please review the 
        <a href="https://docs.google.com/document/d/18tocsvWVEZ8xFNBvz8-88AAK9CnIbqlU7jkXd4G_FvQ/edit?usp=sharing" target="_blank" rel="noopener noreferrer">Master Rules Document</a>.
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

  .rules-content {
    padding: 2rem;
    max-width: 800px;
    margin: 0 auto;
    background: white;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  .rules-content h2 {
    font-family: 'Roboto', sans-serif;
    font-size: 2rem;
    color: #485077;
    margin-bottom: 1rem;
  }

  .rules-content h3 {
    font-family: 'Roboto', sans-serif;
    font-size: 1.5rem;
    color: #485077;
    margin-top: 1.5rem;
    margin-bottom: 0.5rem;
  }

  .rules-content p, .rules-content ul {
    font-family: 'Montserrat', sans-serif;
    font-size: 1.1rem;
    color: #485077;
    margin-bottom: 1.5rem;
    line-height: 1.6;
  }

  .rules-content ul {
    list-style-type: disc;
    padding-left: 1.5rem;
  }

  .rules-content a {
    color: #485077;
    text-decoration: underline;
    transition: color 0.3s ease;
  }

  .rules-content a:hover {
    color: #fed893;
  }

  /* Mobile Styling */
  @media (max-width: 768px) {
    .page-title {
      font-size: 2rem;
      height: 8rem;
    }

    .rules-content {
      padding: 1.5rem;
    }

    .rules-content h2 {
      font-size: 1.6rem;
    }

    .rules-content h3 {
      font-size: 1.3rem;
    }

    .rules-content p, .rules-content ul {
      font-size: 1rem;
    }
  }
</style>
