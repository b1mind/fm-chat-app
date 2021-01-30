<script>
  import { onMount } from 'svelte'
  import { gsap } from 'gsap'
  import Phone from './components/Phone.svelte'

  let main

  //fixme: mousemove animation not quite working
  /*   function movePhone(e) {
    const clientHeight = main.clientHeight
    const clientWidth = main.clientWidth
    const { offsetX, offsetY, target } = e

    const xPos = offsetX / clientWidth - 0.5
    const yPos = offsetY / clientHeight - 0.5

    gsap.to('.phone-wrap', {
      duration: 1,
      x: xPos * 20,
      y: yPos * 30,
      rotateX: yPos * 40,
      rotateY: xPos * 10,
      ease: 'power3.out',
    })
  } */

  onMount(() => {
    const heroItems = main.firstChild.children
    const tlIntro = gsap.timeline({
      defaults: { duration: 0.5 },
    })

    tlIntro
      .from(heroItems[1].children, { autoAlpha: 0, y: 100, stagger: -0.3 })
      .from(heroItems[0], { autoAlpha: 0, x: 200 })
  })
</script>

<!-- <main on:mousemove|stopPropagation={movePhone}> -->
<main bind:this={main}>
  <div class="hero">
    <Phone />
    <div class="hero-text">
      <h1>Book with Us</h1>
      <p>
        Play with this interactive booking chat app demo made with Svelte. This layout was
        a challenge from Kevin Powell to his Demystified CSS class based on a
        FrontendMentors design.
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
    min-height: 920px;
    display: grid;
    place-content: center;
    background-color: var(--clr-gray);
    overflow: hidden;
    perspective: 1900px;
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
      @media (max-width: 1080px) {
        height: 625px;
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
      @media (max-width: 1080px) {
        height: 625px;
      }
    }
  }

  .hero {
    width: 900px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 2fr;

    &-text {
      max-width: 45ch;
      justify-self: flex-end;
      align-self: center;
      font-size: 1.05rem;
    }

    @media (max-width: 1080px) {
      width: 100%;
      padding: 1rem;
      grid-template-columns: 1fr;
      justify-items: center;
    }
  }

  h1 {
    color: var(--clr-two-dark);
    font-size: 2.75rem;
    font-weight: 600;
  }

  p {
    color: #797979;
  }

  //< end me
</style>
