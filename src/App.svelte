<script>
  import Card from './components/Card.svelte'
</script>

<main>
  <div class="hero">
    <Card />
    <div class="hero-text">
      <h1>Book with Us</h1>
      <p>
        Stay in touch with this amazing Svelte app by booking a appointment. Play around
        as there maybe many fun working features to this challenge by Kevin Powell based
        on Frontend Mentors
      </p>
    </div>
  </div>
</main>

<style lang="scss">
  //< style more

  $max: 1900px;
  $min: 360px;

  main {
    position: relative;
    margin: 0 auto;
    max-width: $max;
    min-height: 920px;
    display: grid;
    place-content: center;
    background-color: var(--clr-gray);
    overflow: hidden;
    z-index: 0;

    &::before {
      content: '';
      position: absolute;
      width: 500px;
      height: 775px;
      top: 0;
      left: -75px;
      border-radius: 0 0 400px 400px;
      background: linear-gradient(var(--clr), var(--clr-two));
      z-index: -1;
    }

    &::after {
      content: '';
      width: 450px;
      height: 800px;
      bottom: 0;
      right: 0;
      position: absolute;
      border-radius: 400px 400px 0 0;
      opacity: 0.03;
      background: var(--clr);
      z-index: -1;
    }
  }

  .hero {
    width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 2fr;
    place-content: center;
    &-text {
      width: 50ch;
      justify-self: flex-end;
      align-self: center;
      font-size: 1.05rem;
    }
  }

  h1 {
    font-size: 2.75rem;
    font-weight: 600;
  }

  //< end me
</style>
