// Signing out the user account by importing the username from the store
<script>
  import { username, user } from './user';

  // Implementing a function called signout that will call leave() on the user and sets the
  // username store to an empty string!
  function signout() {
    user.leave();
    username.set('');
  }
</script>

<!-- HTML to implement the signout button in the UI, and also to display the username as the header -->
<header>
<h1>CSU33D03</h1>
  {#if $username} <!-- Checking to see if the username is present and display it in the HEADER -->
    <div class="user-bio">
      
      <span>Hello <strong>{$username}</strong></span>

      <!-- // The following is a cute API which will smartly create an avatar with the users intials -->
      <img src={`https://avatars.dicebear.com/api/initials/${$username}.svg`} alt="avatar" /> 
    </div>

    <button class="signout-button" on:click={signout}>Log Out</button>

    {:else}

      <h3>p2p Chat By Vanaj & Chhavinder</h3>
  {/if}
</header>