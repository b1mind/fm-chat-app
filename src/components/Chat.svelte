<div class="chat-messages">
  <div class="chat-bubble">That sounds like a great idea.</div>

  <div class="chat-bubble">
    Can you send me any example pictures or story board ideas?
  </div>

  <div class="chat-bubble is-img">
    <img src="https://picsum.photos/50/" alt="avatar" />
    <img src="https://picsum.photos/50/" alt="avatar" />
    <img src="https://picsum.photos/50/" alt="avatar" />
  </div>

  <div class="chat-bubble is-user">This is an example of what I need</div>

  <div class="chat-bubble is-user">Can we do this asap?</div>

  <div class="chat-bubble">Definitely can! Lets get it done pick a starting budget.</div>

  <div class="chat-bubble is-option">
    <label class="container">
      <span class="radio-label">
        Entry package 1h <span>$69</span>
      </span>
      <input class="radio" name="option" type="radio" />
      <!-- prettier-ignore -->
      <span class="radio-control"></span>
    </label>
  </div>

  <div class="chat-bubble is-option">
    <label class="container">
      <span class="radio-label">
        Full package 8h <span>$420</span>
      </span>
      <input class="radio" name="option" type="radio" />
      <!-- prettier-ignore -->
      <span class="radio-control"></span>
    </label>
  </div>
</div>

<style lang="scss">
  .chat-messages {
    position: relative;
    bottom: 0;
    padding: 0.5rem;
    display: grid;
  }

  .chat-bubble {
    width: max-content;
    max-width: 70%;
    height: min-content;
    margin: 0.25rem 0;
    padding: 0.5rem;
    color: var(--clr);
    font-size: 0.55rem;
    background-color: var(--clr-two-gray);
    border-radius: 10px 10px 10px 3px;
  }

  .is-user {
    justify-self: flex-end;
    color: var(--clr-black);
    background-color: var(--clr-white);
    border-radius: 10px 10px 3px 10px;
    box-shadow: 0px 3px 7px 2px #1b1b1b10;
  }

  .is-img {
    max-width: 80%;
    margin: 0.5rem 0 0 0;
    padding: 0;
    background-color: transparent;
    justify-self: flex-end;

    img {
      border-radius: 10px;
    }
  }

  .is-option {
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
    display: block;
    position: relative;
    padding-left: 20px;
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
    top: 5px;
    left: 0;
    height: 15px;
    width: 15px;
    background-color: transparent;
    border-radius: 50%;
    border: 2px solid var(--clr-two);
    cursor: pointer;
  }

  .container input:hover ~ .radio-control {
    background-color: var(--clr-two);
  }

  .container input:checked ~ .radio-control {
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
    left: 25%;
    top: 25%;
    width: 50%;
    height: 50%;
    border-radius: 50%;
    background-color: var(--clr-white);
    border: 1px solid transparent;
  }
</style>
