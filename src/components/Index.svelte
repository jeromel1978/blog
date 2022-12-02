<script lang="ts">
  import Login from "./Login.svelte";
  import Main from "./Main.svelte";
  let LoggedIn = false;
  const ConfirmLogIn = () => {
    LoggedIn = true;
  };
</script>

{#if LoggedIn}
  <Main />
{:else}
  <Login on:loggedin={ConfirmLogIn} />
{/if}
