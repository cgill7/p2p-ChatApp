<script>
  export let message;
  export let sender;

  const messageClass = message.who === sender ? 'sent' : 'received';

  // Using the API - dicebear to view the avatar along with the message sent from the user
  const avatar = `https://avatars.dicebear.com/api/initials/${message.who}.svg`;

  const ts = new Date(message.when);
</script>

<div class={`message ${messageClass}`}>
  <img src={avatar} alt="avatar" />
  <div class="message-text">
    <p>{message.what}</p>

    <time>{ts.toLocaleTimeString()}</time>
  </div>
</div>
