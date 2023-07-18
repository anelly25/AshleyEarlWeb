<template>
  <nav class="navbar">
    <div class="navbar-content">
      <h1>Ashley Earl Law Firm</h1>
      <p>Call: <a class="phone-link" :href="'tel:+12257619456'">(225)761-9456</a></p>
      <div class="menu-container">
        <button class="dropdown-toggle" @click="toggleDropdown">
          <span class="dropdown-line"></span>
          <span class="dropdown-line"></span>
          <span class="dropdown-line"></span>
        </button>
        <div class="navbar-links" v-if="showDropdown">
          <button class="nav-link" @click="showHome">Home</button>
          <button class="nav-link" @click="showContact">Contact</button>
          <button class="nav-link" @click="showPracticeArea">Practice Area</button>
        </div>
      </div>
    </div>
    <div class="content-container">
      <HomeView :show="showHomeComponent" />
      <ContactForm v-if="showContactComponent" />
      <PracticeAreas v-if="showPracticeAreaComponent" />
    </div>
  </nav>
</template>

<script>
import HomeView from './HomeView.vue';
import ContactForm from './ContactForm.vue';
import PracticeAreas from './PracticeAreas.vue';

export default {
  name: 'NavbarView',
  components: {
    HomeView,
    ContactForm,
    PracticeAreas,
  },
  data() {
    return {
      showDropdown: false,
      showHomeComponent: true,
      showContactComponent: false,
      showPracticeAreaComponent: false,
    };
  },
  methods: {
    toggleDropdown() {
      this.showDropdown = !this.showDropdown;
    },
    showHome() {
      this.showHomeComponent = true;
      this.showContactComponent = false;
      this.showPracticeAreaComponent = false;
    },
    showContact() {
      this.showHomeComponent = false;
      this.showContactComponent = true;
      this.showPracticeAreaComponent = false;
    },
    showPracticeArea() {
      this.showHomeComponent = false;
      this.showContactComponent = false;
      this.showPracticeAreaComponent = true;
    },
  },
};
</script>

<style scoped>
.content-container {
  height: 100vh; /* Adjust as needed */
  overflow-y: auto;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100px; 
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
  font-size: 2em; 
  margin: 0;
}

.navbar-content p {
  margin: 0;
  font-size: 1.5em; 
}

.navbar-content .phone-link {
  color: white !important;
  text-decoration: none !important;
}

.menu-container {
  position: relative;
}

.dropdown-toggle {
  background: transparent;
  border: none;
  cursor: pointer;
}

.dropdown-line {
  width: 25px;
  height: 3px;
  background-color: #fff;
  margin: 4px 0;
  display: block;
}

.navbar-links {
  position: absolute;
  background-color: #333;
  padding: 10px;
  right: 0;
  top: 40px; /* Adjust this value as needed */
}

.navbar-links .nav-link {
  color: #fff;
  display: block;
  padding: 5px 0;
}

.navbar-content .active {
  font-weight: bold;
}
</style>
