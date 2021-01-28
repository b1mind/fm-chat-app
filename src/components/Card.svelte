<script>
  console.log('lets make a chat scheduling app?')
</script>

<div class="phone-wrap">
  <div class="phone">
    <div class="chat-header">
      <div class="user">
        <b>-</b>

        <div class="user-avatar">
          <img src="https://picsum.photos/50/" alt="avatar" />
        </div>

        <div class="user-title">
          <h2>Some person</h2>
          <h3>their title</h3>
        </div>
        <ul class="menu">
          <li />
          <li />
          <li />
        </ul>
      </div>
    </div>

    <div class="chat-body">
      <div class="chat-bubble">This will be a msg</div>
      <div class="chat-bubble">This will be a msg</div>
      <div class="chat-bubble">This will be a msg</div>
      <div class="chat-bubble">This will be a msg</div>
      <div class="chat-input">
        <input type="text" placeholder="type a message" />
        <button>c</button>
      </div>
    </div>
  </div>
</div>

<style type="text/scss">
  .phone-wrap {
    width: min-content;
    padding: 10px;
    background-color: var(--clr-white);
    border-radius: 25px;
  }

  .phone {
    width: 250px;
    height: 500px;
    border-radius: 20px;
    background-color: var(--clr-gray);
  }

  .chat-header {
    position: relative;
    width: 100%;
    color: var(--clr-white);
    border-radius: 20px 20px 5px 5px;
    background: linear-gradient(-90deg, var(--clr), var(--clr-two));
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
    padding: 0 0.5rem;
  }

  .chat-input {
    height: 35px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    background-color: var(--clr-white);
    border-radius: 20px;

    input {
      margin-left: 10px;
      border: none;
    }

    button {
      width: 25px;
      height: 25px;
      margin-right: 10px;
      color: var(--clr-white);
      background-color: var(--clr-black);
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
      background-color: var(--clr-black);
      border: 2px solid var(--clr-white);
      border-radius: 50%;
      overflow: hidden;
    }

    &-title {
      justify-self: flex-start;

      h2 {
        margin: 0;
        font-size: 1.1rem;
      }

      h3 {
        margin: 0;
        color: var(--clr-gray);
        font-size: 0.7rem;
        font-weight: 400;
      }
    }
  }

  .menu {
    width: 5px;
    display: grid;
    gap: 2px;
    justify-self: flex-end;

    li {
      width: 2px;
      height: 2px;
      background-color: var(--clr-white);
    }
  }
</style>
