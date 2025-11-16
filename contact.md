---
layout: default
title: Contact Me
---

# Contact Me

Fill out the form below to send me an email:

![Contact Me](https://media.giphy.com/media/O56JjOpDoljTG/giphy.gif){: .img-center }

<form id="contact-form" action="https://formspree.io/f/myzlnqqn" method="POST">
  <label for="name">Name:</label><br>
  <input type="text" id="name" name="name" required><br><br>

  <label for="email">Email:</label><br>
  <input type="email" id="email" name="email" required><br><br>

  <label for="message">Message:</label><br>
  <textarea id="message" name="message" rows="5" required></textarea><br><br>

  <button type="submit">Send</button>
</form>

<script>
document.getElementById('contact-form').addEventListener('submit', function(e) {
  e.preventDefault(); // prevent default submit
  fetch(this.action, {
    method: this.method,
    body: new FormData(this),
    headers: { 'Accept': 'application/json' }
  }).then(response => {
    if (response.ok) {
      window.location.href = '/thank-you'; // redirect on success
    } else {
      alert('Oops! There was a problem submitting your form.');
    }
  });
});
</script>
