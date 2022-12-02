<script lang="ts">
  import { createEventDispatcher } from "svelte";
  let userid: string;
  let password: string;

  const dispatch = createEventDispatcher();
  const Login = () => {
    dispatch("loggedin");
  };
  $: CantLogin = !userid && !password;
</script>

<div>
  <input type="text" bind:value={userid} placeholder="User ID" />
  <input type="password" bind:value={password} placeholder="Password" />
  <button on:click={Login} disabled={CantLogin}>Login</button>
</div>
