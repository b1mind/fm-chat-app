<script>
  console.log('lets make a chat scheduling app?')
</script>

<div class="phone-wrap">
  <div class="phone">
    <div class="chat-header">
      <div class="user">
        <b>&lt;</b>

        <div class="user-avatar">
          <img src="https://picsum.photos/50/" alt="avatar" />
        </div>

        <div class="user-title">
          <h2>Some Person</h2>
          <h3>Available for service</h3>
        </div>
        <ul class="menu">
          <li />
          <li />
          <li />
        </ul>
      </div>
    </div>

    <div class="chat-body">
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

        <div class="chat-bubble">
          Definitely can! Lets get it done pick a starting budget.
        </div>

        <div class="chat-options">
          <div class="options-box">
            <input type="radio" />
          </div>

          <div class="options-box">
            <input type="radio" />
          </div>
        </div>
      </div>
    </div>

    <div class="chat-input">
      <input type="text" placeholder="type a message" />

      <b>&gt;</b>
    </div>
  </div>
</div>

<style type="text/scss">
  //style like its 1999

  b,
  .menu {
    cursor: pointer;
  }

  .phone-wrap {
    width: min-content;
    padding: 10px;
    background-color: var(--clr-white);
    border-radius: 25px;
    box-shadow: 10px 10px 20px 1px #1b1b1b20;
  }

  .phone {
    position: relative;
    width: 250px;
    height: 500px;
    border-radius: 20px;
    background-color: var(--clr-dark-gray);
    overflow: hidden;
  }

  .chat-header {
    position: relative;
    width: 100%;
    color: var(--clr-white);
    border-radius: 20px 20px 5px 5px;
    background: linear-gradient(-90deg, var(--clr), var(--clr-two));
    box-shadow: 0px 5px 10px 5px #1b1b1b20;

    &::before {
      position: relative;
      content: '';
      width: 125px;
      height: 20px;
      margin: 0 auto;
      display: block;
      border-radius: 0 0 10px 10px;
      background-color: var(--clr-white);
    }
  }

  .chat-body {
    height: 385px;
    padding: 0 0.5rem;
  }

  .chat-messages {
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

  .chat-input {
    height: 35px;
    margin: 0 7px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: var(--clr-white);
    border-radius: 20px;

    input {
      margin-left: 10px;
      border: none;
    }

    b {
      width: 25px;
      height: 25px;
      margin-right: 5px;
      color: var(--clr-white);
      text-align: center;
      background-color: var(--clr-two-dark);
      border: none;
      border-radius: 50%;
    }
  }

  .user {
    padding: 10px 15px;
    display: grid;
    grid-template-columns: 1fr 1fr 6fr 1fr;
    gap: 0.5rem;
    align-items: center;

    b {
      justify-self: flex-end;
    }

    &-avatar {
      width: 30px;
      height: 30px;
      border: 2px solid var(--clr-white);
      border-radius: 50%;
      overflow: hidden;
    }

    &-title {
      justify-self: flex-start;

      h2 {
        margin: 0;
        font-size: 1rem;
        font-weight: 400;
        line-height: 1rem;
      }

      h3 {
        margin: 0;
        color: var(--clr-gray);
        opacity: 0.75;
        font-size: 0.55rem;
        letter-spacing: 0.055rem;
        font-weight: 300;
      }
    }
  }

  .menu {
    width: 5px;
    display: grid;
    gap: 2px;
    justify-self: flex-end;

    li {
      width: 3px;
      height: 3px;
      background-color: var(--clr-white);
    }
  }
</style>
