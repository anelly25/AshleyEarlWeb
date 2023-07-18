<template>
  <nav class="navbar">
    <div class="navbar-content">
      <h1>Ashley Earl Law Firm</h1>
      <p>Call: <a class="phone-link" :href="'tel:+12257619456'">(225)761-9456</a></p>
      <button @click="toggleLanguage">{{ toggleButtonText }}</button>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavbarView',
  data() {
    return {
      language: 'english',
    };
  },
  computed: {
    navTitle() {
      return this.language === 'english' ? 'Ashley Earl Law Firm' : 'Firma de Abogados de Ashley Earl';
    },
    callText() {
      return this.language === 'english' ? 'Call' : 'Llama';
    },
    toggleButtonText() {
      return this.language === 'english' ? 'Español' : 'English';
    },
  },
  methods: {
    toggleLanguage() {
      this.language = this.language === 'english' ? 'spanish' : 'english';
    },
  },
};
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px; /* Increased height */
  background-color: #333;
  z-index: 9999;
}

.navbar-content {
  max-width: 800px;
  margin: 0 auto;
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  color: #fff;
}

.navbar-content h1 {
  font-size: 2em; /* Increased font size */
  margin: 0;
}

.navbar-content p {
  margin: 0;
  font-size: 1.5em; /* Increased font size */
}

.navbar-content .phone-link {
  color: white !important;
  text-decoration: none !important;
}

.navbar-content .phone-link:hover,
.navbar-content .phone-link:focus {
  color: white !important;
  text-decoration: underline !important;
}
</style>
