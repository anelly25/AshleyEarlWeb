<template>
  <div class="contact-form">
    <h2>Contact Form</h2>
    <form @submit.prevent="sendEmail" ref="form">
      <label for="from_name">Your Name</label>
      <input type="text" id="from_name" v-model="from_name" name="from_name">
      <input type="text" id="to_name" v-model="to_name" name="to_name">
      <label for="email">Your Email</label>
      <input v-model="userEmail" type="email" placeholder="Your email" name="user_email">
      <label for="message">Your Message</label>
      <textarea id="message" v-model="message" name="message"></textarea>
      <p class="disclaimer-text">By submitting this form, you are agreeing to receive promotional email and text communications from the Ashly Earl Law Firm.</p>
      <div class="button-container">  
        <button type="submit" class="save-button">Send Email</button>
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
.disclaimer-text {
  font-size: 12px; /* Smaller font size for the disclaimer text */
  margin-bottom: 20px; /* Space between the disclaimer text and the button */
}

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

.button-container {
  display: flex;
  justify-content: center; /* Align the button to the center */
}

.save-button {
  background-color: green;
  color: white;
  padding: 10px 15px; 
  font-size: 16px; 
  border-radius: 5px; /* Make it rectangular */
  width: 100%; /* Make it long */
  max-width: 300px; /* Control the maximum width */
  transition: all 0.2s;
  cursor: pointer;
}

.save-button:hover {
  background-color: darkgreen;
}
</style>