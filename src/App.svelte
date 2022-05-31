<script>
  import User from "./database/user.json";
  import UserList from "./lib/UserList.svelte";
</script>

<main>
  <h1>Hello world!</h1>

  <UserList {User} />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  main {
    width: 400px;
    margin: auto;
  }

  h1 {
    text-align: center;
    margin-bottom: 1.25rem;
  }
</style>
