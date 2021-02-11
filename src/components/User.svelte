<script>
  export let user = {
    name: 'Brent Morton',
    title: 'available for work',
    avatar: 'https://picsum.photos/25/',
  }
</script>

<div class="user">
  <b>&lt;</b>

  <div class="user-avatar">
    <img src="{user.avatar}" alt="avatar" width="25px" height="25px" />
  </div>

  <div class="user-title">
    <h2>{user.name}</h2>
    <h3>{user.title}</h3>
  </div>

  <ul class="menu">
    <li></li>
    <li></li>
    <li></li>
  </ul>
</div>

<style lang="scss">
  .user {
    padding: 10px 15px;
    display: grid;
    grid-template-columns: 1fr 1fr 100fr 1fr;
    gap: 0.5rem;
    align-items: center;

    b {
      padding: 0 3px;
      cursor: pointer;
    }

    &-avatar {
      width: 25px;
      height: 25px;
      border: 2px solid var(--clr-white);
      border-radius: 50%;
      overflow: hidden;
    }

    &-title {
      justify-self: flex-start;

      h2 {
        margin: 0;
        font-size: 0.9rem;
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
    padding: 0 5px;
    display: grid;
    gap: 2px;
    cursor: pointer;

    li {
      width: 3px;
      height: 3px;
      background-color: var(--clr-white);
    }
  }
</style>
