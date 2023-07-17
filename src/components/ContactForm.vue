<template>
  <div class="contact-form">
    <button @click="$emit('exit')">Exit</button>
    <h2>Contact Form</h2>
    <form @submit.prevent="sendEmail" ref="form">
      <label for="from_name">Your Name</label>
      <input type="text" id="from_name" v-model="from_name" name="from_name">

      <label for="email">Your Email</label>
      <input v-model="userEmail" type="email" placeholder="Your email" name="user_email">

      <label for="message">Your Message</label>
      <textarea id="message" v-model="message" name="message"></textarea>

      <div>  
        <button type="submit">Send Email</button>
      </div>
    </form>
  </div>
</template>

<script>
import emailjs from 'emailjs-com';

export default {
  name: 'ContactForm',
  data() {
    return {
      from_name: '',
      to_name: 'Earl Law Firm',
      userEmail: '',
      message: '',
    }
  },
  mounted() {
    emailjs.init('ShDD2sDEjAfzRK-z_');
  },
  methods: {
    sendEmail() {
      emailjs.sendForm('service_j63dlsp', 'template_4yijbnc', this.$refs.form)
    .then((result) => {
      console.log('SUCCESS!', result.status, result.text);
    })
    .catch((error) => {
      console.error('Error while sending the email:', error);
    });
    }
  }
}
</script>

<style scoped>
.contact-form {
  padding: 20px;
  max-width: 600px;
  margin: 80px auto;
  background-color: #f9f9f9;
  border-radius: 4px;
}

.contact-form label {
  display: block;
  margin: 10px 0;
}

.contact-form input,
.contact-form textarea {
  width: 100%;
  padding: 10px;
  margin-bottom: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
}

.contact-form textarea {
  height: 150px;
  resize: vertical;
}
</style>
