<template>
  <nav class="navbar">
    <div class="navbar-content">
      <h1>Earl Law Firm</h1>

      <div class="tab-container">
  <button class="tab-link" :class="{'active-tab': showHomeComponent}" @click="showHome">Home</button>
  <button class="tab-link" :class="{'active-tab': showContactComponent}" @click="showContact">Contact</button>
  <button class="tab-link" :class="{'active-tab': showPracticeAreaComponent}" @click="showPracticeArea">Practice Areas</button>
  <button class="tab-link" :class="{'active-tab': showPrivacyNoticeComponent}" @click="showPrivacyNotice">Privacy Notice</button>
</div>


      <p>Call: <a class="phone-link" :href="'tel:+12257619456'">(225)761-9456</a></p>
    </div>

    <div class="content-container">
      <HomeView v-if="showHomeComponent" @showPracticeAreas = "showPracticeArea"/>
      <ContactForm v-if="showContactComponent" @emailSent="showHome" />
      <PracticeAreas v-if="showPracticeAreaComponent"  />
      <div v-if="showPrivacyNoticeComponent" class="privacy-notice">
        <h2>Privacy Notice</h2>
        <p>Welcome to Earl Law Firm! We are committed to protecting your privacy and ensuring that your personal data is handled responsibly. This privacy notice explains how we collect, use, and protect your information. Please read it carefully.</p>
        <h3>Data Controller</h3>
        <ul>
          <li>Organization Name: Earl Law Firm</li>
          <li>Contact Details: secretary@earllawfirm.com</li>
          <li>Data Protection Officer (DPO): Ashly Van Earl</li>
        </ul>
        <h3>What Personal Data We Collect</h3>
        <p>We collect the following types of personal data:</p>
        <ul>
          <li>Contact Information: Includes names, email addresses, phone numbers, and mailing addresses.</li>
          <li>Usage Data: Information about how you interact with our website, such as pages visited, time spent, and browser details.</li>
          <li>Cookies and Analytics: We use cookies and similar technologies to analyze website traffic and improve user experience.</li>
        </ul>
        <h3>How We Use Your Personal Data</h3>
        <p>We process your personal data for the following purposes:</p>
        <ul>
          <li>Communication: To respond to your inquiries and provide customer support.</li>
          <li>Marketing: To send you relevant updates, newsletters, and promotional materials (if you’ve opted in).</li>
          <li>Analytics: To understand user behavior and enhance our website’s performance.</li>
        </ul>
        <h3>Legal Basis for Processing</h3>
        <p>We process your data based on the following legal grounds:</p>
        <ul>
          <li>Contractual Necessity: To fulfill our contractual obligations with you.</li>
          <li>Legitimate Interests: To improve our services and enhance user experience.</li>
          <li>Consent: For marketing communications (if applicable).</li>
        </ul>
        <h3>Data Retention</h3>
        <p>We retain your personal data for as long as necessary to achieve the purposes outlined in this notice. When no longer needed, we securely delete or anonymize it.</p>
        <h3>Your Rights</h3>
        <p>You have the right to:</p>
        <ul>
          <li>Access your personal data.</li>
          <li>Correct any inaccuracies.</li>
          <li>Request erasure (in certain cases).</li>
          <li>Object to processing.</li>
          <li>Data portability.</li>
        </ul>
      </div>
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
    showPrivacyNoticeComponent: false,
  };
},
methods: {
  showHome() {
    this.showHomeComponent = true;
    this.showContactComponent = false;
    this.showPracticeAreaComponent = false;
    this.showPrivacyNoticeComponent = false;
  },
  showContact() {
    this.showHomeComponent = false;
    this.showContactComponent = true;
    this.showPracticeAreaComponent = false;
    this.showPrivacyNoticeComponent = false;
  },
  showPracticeArea() {
    this.showHomeComponent = false;
    this.showContactComponent = false;
    this.showPracticeAreaComponent = true;
    this.showPrivacyNoticeComponent = false;
  },
  showPrivacyNotice() {
    this.showHomeComponent = false;
    this.showContactComponent = false;
    this.showPracticeAreaComponent = false;
    this.showPrivacyNoticeComponent = true;
  }
}

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
  height: 8rem; /* use rem instead of px for better responsiveness */
  background-color: #f6b101;
  z-index: 9999;
  border-bottom: 1px solid black;
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
  padding: 1rem 2rem; /* Adjust padding for finer control over tab spacing */
  margin: 0 1rem; /* Add space between tabs */
  border: none;
  background: none;
  cursor: pointer;
  color: #333;
  font-size: 1em;
  transition: color 0.3s;
}
.privacy-notice {
  font-size: 0.8em; /* Reduces the font size */
}

.privacy-notice ul {
  list-style: none; /* Removes bullet points */
  padding-left: 0; /* Removes indentation of list */
}

.tab-link::after { /* This will be the line under the tab */
  content: "";
  position: absolute; /* Absolute positioning related to the tab */
  bottom: 0; /* Position the line at the bottom of the tab */
  left: 0; /* Start the line from the left edge of the tab */
  height: 4px; /* Adjust the thickness of the line */
  width: 100%; /* Set the width of the line to be the same as the tab content */
  box-sizing: content-box; /* Include padding in the element's total width and height */
  background: rgba(255, 254, 254, 0.991);
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
@media screen and (max-width: 480px) {
  .navbar-content h1 {
    font-size: 1.2em; /* adjust size for small screens */
  }
  .phone-link {
    font-size: .5em;
  }
  
  .navbar {
    height: 100vm; /* adjust height for small screens */
  }

  .tab-link {
    padding: 0.5rem 1rem; /* adjust padding for small screens */
    margin: 0 0.3rem; /* adjust margin for small screens */
    font-size: 0.7em; /* adjust font size for small screens */
  }

  .tab-link::after { /* This will be the line under the tab */
    height: 2px; /* adjust the thickness of the line for small screens */
  }
  
  .navbar-content p {
    font-size: 0.8em; /* adjust font size for small screens */
  }
  .content-container{
    height:100vh;
    overflow-y: auto;
  }
}
</style>

