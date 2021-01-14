<template>
  <div>
    <h2>Contact Us</h2>
    <slot name="top"></slot>

    <form>
      <div class="form-group">
        <label for="yourName">Your name</label>
        <input type="text" class="form-control" id="yourName" placeholder="Enter your name">
      </div>

      <div class="form-group">
        <label for="emailAddress">E-mail address</label>
        <input type="email" class="form-control" id="emailAddress" placeholder="Enter your e-mail address">
      </div>

      <slot></slot>

      <div class="form-group">
        <label for="message">Message</label>
        <textarea id="message" cols="30" rows="10" class="form-control" placeholder="Enter your message"></textarea>
      </div>

      <slot name="bottom">
        <p>We will respond within 2 business days.</p>
      </slot>

      <button type="submit" class="btn btn-primary">Send</button>
    </form>
  </div>
</template>

<script>
  export default {

  }
</script>
