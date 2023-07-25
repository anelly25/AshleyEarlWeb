<template>
  <nav class="navbar">
    <div class="navbar-content">
      <h1>Ashley Earl Law Firm</h1>

      <div class="tab-container">
        <button class="tab-link" :class="{'active-tab': showHomeComponent}" @click="showHome">Home</button>
        <button class="tab-link" :class="{'active-tab': showContactComponent}" @click="showContact">Contact</button>
        <button class="tab-link" :class="{'active-tab': showPracticeAreaComponent}" @click="showPracticeArea">Practice Area</button>
      </div>

      <p>Call: <a class="phone-link" :href="'tel:+12257619456'">(225)761-9456</a></p>
    </div>

    <div class="content-container">
      <HomeView v-if="showHomeComponent" @showPracticeAreas = "showPracticeArea"/>
      <ContactForm v-if="showContactComponent" />
      <PracticeAreas v-if="showPracticeAreaComponent"  />
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
      showHomeComponent: true,
      showContactComponent: false,
      showPracticeAreaComponent: false,
    };
  },
  methods: {
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
  height: 100vh;
  overflow-y: auto;
}

.navbar-content h1 {
  font-size: 2em;
  margin: 0;
}

.navbar-content .phone-link {
  color: #001f3f !important;
  text-decoration: none !important;
}

.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 6.25rem; /* 100px */
  background-color: #fff;
  z-index: 9999;
  border-bottom: 0.0625rem solid black; /* 1px */
}

.navbar-content {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-around; /* Changed from 'space-between' to 'space-around' */
  align-items: center;
  color: #333;
}

.tab-container {
  display: flex;
  justify-content: center;
  order: 2;
}

.tab-link {
  display: inline-block; /* Make the tabs inline elements */
  position: relative; /* Set relative positioning for the tabs */
  padding: 1.25rem 1.875rem; /* 20px 30px */
  margin: 0 0.625rem; /* 0 10px */
  border: none;
  background: none;
  cursor: pointer;
  color: #333;
  font-size: 1em;
  transition: color 0.3s;
}

.tab-link::after { /* This will be the line under the tab */
  content: "";
  position: absolute; /* Absolute positioning related to the tab */
  bottom: 0; /* Position the line at the bottom of the tab */
  left: 0; /* Start the line from the left edge of the tab */
  height: 0.25rem; /* 4px */
  width: 100%; /* Set the width of the line to be the same as the tab content */
  box-sizing: content-box; /* Include padding in the element's total width and height */
  background: lightgray;
}

.tab-link:hover {
  color: #001f3f;
}

.active-tab {
  color: #001f3f;
  font-weight: bold;
}

.active-tab::after { /* The line under the active tab */
  background: navy;
}

.navbar-content p {
  order: 3;
}
</style>
