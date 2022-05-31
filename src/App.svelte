<script>
  import User from "./database/user.json";
  let users = User;
  let search;

  const fillterItems = () => {
    let userFillter = User.filter((v) => v.name.includes(search));

    console.log(userFillter);

    users = userFillter;
  };
</script>

<main>
  <h1>Hello world!</h1>

  <input
    type="text"
    placeholder="search data"
    bind:value={search}
    on:input={fillterItems}
  />

  {#if users.length === 0}
    <div class="notification">No Data</div>
  {:else}
    <ul>
      {#each users as user, i}
        <li>
          <div>
            <h2>{i + 1}. {user.name}</h2>
            <h3>{user.gender}</h3>
            <h3>{user.age}</h3>
            <h3>{user.email}</h3>
            <h3>{user.company}</h3>
            <h3>{user.balance}</h3>
          </div>
        </li>
      {/each}
    </ul>
  {/if}
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  h1 {
    text-align: center;
    margin-bottom: 1.25rem;
  }

  input {
    width: 100%;
    padding: 1rem;
    border-radius: 50px;
    margin-bottom: 1rem;
  }

  li {
    padding: 2rem;
    margin-bottom: 2rem;
    background-color: bisque;
    border-radius: 16px;
  }

  .notification {
    text-align: center;
    color: white;
    font-weight: bold;
    margin: 0.5rem;
    padding: 1rem;
    border-radius: 16px;
    background-color: crimson;
  }
</style>
