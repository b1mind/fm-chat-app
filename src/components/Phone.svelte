<script>
  import User from './User.svelte'
  import Chat from './Chat.svelte'

  let msgs = [
    {
      user: false,
      img: false,
      imgs: [],
      option: false,
      msg: 'This is a msg',
    },
    {
      user: true,
      img: false,
      imgs: [],
      option: false,
      msg: 'This is a user msg',
    },
    {
      user: false,
      img: true,
      imgs: [
        { url: 'https://picsum.photos/50/' },
        { url: 'https://picsum.photos/50/' },
        { url: 'https://picsum.photos/50/' },
      ],
      option: false,
      msg: '',
    },
  ]
</script>

<div class="phone-wrap">
  <div class="phone">
    <div class="chat-header">
      <User />
    </div>

    <div class="chat-body">
      <div class="chat-messages">
        {#each msgs as msg}
          <Chat user={msg.user} img={msg.img} imgs={msg.imgs} option={msg.option}>
            {msg.msg}
          </Chat>
        {/each}
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

  b {
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
    position: relative;
    height: 385px;
    overflow-y: scroll;
    &::-webkit-scrollbar {
      width: 0;
      height: 0;
      -ms-overflow-style: none;
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
      outline: transparent;
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

  .chat-messages {
    position: relative;
    bottom: 0;
    padding: 0.5rem;
    display: grid;
  }
</style>
