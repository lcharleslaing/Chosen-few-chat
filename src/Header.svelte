<script>
  import { username, user } from "./user";

  function signout() {
    user.leave();
    username.set("");
  }

  let avatar = `https://api.dicebear.com/7.x/initials/svg?seed=${$username}`;
  console.log("Avatar: ", avatar.toString());
</script>

<header>
  <h1>CF Chat</h1>
  {#if $username}
    <div class="user-bio">
      <span>Hello <strong class="uppercase">{$username}</strong></span>
    </div>

    <button class="signout-button" on:click={signout}>Sign Out</button>
  {:else}
    <h3>Gun.js Chat</h3>
  {/if}
</header>

<style>
  .uppercase {
    text-transform: uppercase;
  }

  .user-bio {
    font-size: x-large;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
