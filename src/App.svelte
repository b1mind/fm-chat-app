<script>
  import Phone from './components/Phone.svelte'

  /*   function movePhone(e) {
    const { offsetX, offsetY, target } = e
    const { clientWidth, clientHeight } = target
    console.dir(e.target)

    const xPos = offsetX / clientWidth - 0.5
    const yPos = offsetY / clientHeight - 0.5
    const modifier = (dex) => dex * 1.2 + 0.5

    gsap.to('.phone-wrap', {
      duration: 1,
      x: xPos * 20,
      y: yPos * 30,
      rotateX: yPos * 40,
      rotateY: xPos * 10,
      ease: 'power3.out',
    })
  } */
</script>

<main>
  <div class="hero">
    <Phone />
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
    perspective: 1000px;
    z-index: 0;

    &::before {
      content: '';
      position: absolute;
      width: 600px;
      height: 775px;
      top: 0;
      left: -75px;
      border-radius: 0 0 400px 400px;
      background: linear-gradient(var(--clr), var(--clr-two));
      z-index: -20;
      @media (max-width: 980px) {
        height: 700px;
      }
    }

    &::after {
      content: '';
      position: absolute;
      width: 650px;
      height: 800px;
      bottom: 0;
      right: -75px;
      border-radius: 400px 400px 0 0;
      background: var(--clr-light);
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
      max-width: 45ch;
      justify-self: flex-end;
      align-self: center;
      font-size: 1.05rem;
    }

    @media (max-width: 980px) {
      width: 100%;
      padding: 1rem;
      grid-template-columns: 1fr;
      place-items: center;
    }
  }

  h1 {
    color: var(--clr-two-dark);
    font-size: 2.75rem;
    font-weight: 600;
  }

  p {
    color: #9d9d9d;
  }

  //< end me
</style>
