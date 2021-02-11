<script>
  import { createEventDispatcher } from 'svelte'
  import { fly } from 'svelte/transition'

  export let option = false
  export let user = false
  export let img = false
  export let imgs = []
  export let price = 420

  const dispatch = createEventDispatcher()

  function confirmMsg() {
    dispatch('confirm', {
      price: price,
    })
  }
</script>

<div
  class="chat-bubble"
  in:fly="{{ y: 20 }}"
  class:option
  class:user
  class:img
  selectedOption
>
  {#if user}
    <slot>That sounds like a great idea.</slot>
  {:else if img}
    {#each imgs as img}
      <img src="{img.url}" alt="avatar" width="50px" height="50px" />
    {/each}
  {:else if option}
    <label class="container" on:click="{confirmMsg}">
      <span class="radio-label">
        <slot>Entry package 1h</slot><span>{` $${price}`}</span>
      </span>

      <input class="radio" name="option" type="radio" value="{price}" />

      <!-- prettier-ignore -->
      <span class="radio-control"></span>
    </label>
  {:else}
    <slot>That sounds like a great idea.</slot>
  {/if}
</div>

<style lang="scss">
  //style like its 1999

  .chat-bubble {
    width: max-content;
    max-width: 70%;
    height: min-content;
    margin: 0.25rem 0;
    padding: 0.5rem;
    color: var(--clr-two-dark);
    font-size: 0.6rem;
    font-weight: 600;
    background-color: var(--clr-two-gray);
    border-radius: 10px 10px 10px 3px;
  }

  .user {
    justify-self: flex-end;
    color: var(--clr-black);
    background-color: var(--clr-white);
    border-radius: 10px 10px 3px 10px;
    box-shadow: 0px 3px 7px 2px #1b1b1b10;
  }

  .img {
    max-width: 80%;
    margin: 0.5rem 0 0 0;
    padding: 0;
    background-color: transparent;
    justify-self: flex-end;

    img {
      margin: 0 2px;
      border-radius: 10px;
    }
  }

  .option {
    color: var(--clr-white);
    background: linear-gradient(90deg, var(--clr), var(--clr-two));
  }

  .radio-label {
    span {
      font-size: 0.85rem;
      font-weight: 700;
    }
  }

  .container {
    display: flex;
    position: relative;
    padding-left: 20px;
    align-items: center;
  }

  /*hide normal input*/
  .container input {
    position: absolute;
    opacity: 0;
    height: 0;
    width: 0;
    cursor: pointer;
  }

  .radio-control {
    position: absolute;
    left: 0;
    height: 16px;
    width: 16px;
    background-color: transparent;
    border-radius: 50%;
    border: 2px solid var(--clr-two);
    cursor: pointer;
  }

  .container input:hover ~ .radio-control {
    border: 2px solid var(--clr-white);
  }

  .radio-control:after {
    content: '';
    position: absolute;
    display: none;
  }

  .container input:checked ~ .radio-control:after {
    display: block;
    // visibility: hidden;
  }

  .container .radio-control:after {
    left: 1px;
    top: 1px;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: var(--clr-two);
    border: 1px solid transparent;
  }
</style>
