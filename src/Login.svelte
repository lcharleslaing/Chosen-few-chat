<script>
  import { user } from "./user";

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>

<div class="flex flex-col gap-1 my-2 justify-center items-center">
  <input
    bind:value={username}
    type="password"
    placeholder="Username..."
    class="input input-bordered w-full max-w-xs"
  />

  <input
    bind:value={password}
    type="password"
    placeholder="Password..."
    class="input input-bordered w-full max-w-xs"
  />
  <div class="flex gap-2">
    <button class="btn btn-lg btn-primary login" on:click={login}>Login</button>
    <button class="btn btn-lg btn-primary login" on:click={signup}
      >Sign Up</button
    >
  </div>
</div>
