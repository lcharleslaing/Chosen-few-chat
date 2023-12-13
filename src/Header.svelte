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
  <h2 class="text-2xl">CF💬</h2>
  {#if $username}
    <div class="user-bio">
      <span>Hello <strong class="uppercase">{$username}</strong></span>
    </div>

    <button class="btn btn-md btn-primary" on:click={signout}>Sign Out</button>
  {:else}
    <h2 class="text-2xl">CF💬</h2>
  {/if}
</header>

<style>
  .uppercase {
    text-transform: uppercase;
  }

  .user-bio {
    font-size: large;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>
