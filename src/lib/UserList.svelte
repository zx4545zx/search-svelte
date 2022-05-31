<script>
  import { fade } from "svelte/transition";

  export let User = [];

  let users = User;
  let search;

  const fillterItems = () => {
    let userFillter = User.filter((v) => v.name.toLowerCase().includes(search));

    users = userFillter;
  };
</script>

<input
  type="text"
  placeholder="search data"
  bind:value={search}
  on:input={fillterItems}
/>

{#if users.length === 0}
  <div class="notification" in:fade={{ delay: 100 }}>No Data</div>
{:else}
  <ul>
    {#each users as user, i}
      <li in:fade={{ delay: 100 }} out:fade={{ delay: 100 }}>
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

<style>
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

  li {
    width: 300px;
    list-style: none;
    padding: 2rem;
    margin: 2rem;
    margin-top: 0;
    background-color: rgb(218, 218, 218);
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

  input {
    width: 100%;
    padding: 1rem;
    background-color: rgb(240, 240, 240);
    border: none;
    border-radius: 50px;
    margin-bottom: 1rem;
  }
</style>
