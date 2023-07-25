<template>       
      <div class="top-container">
    <div class="image-container top-image"></div>
    <div class="image-container bottom-image"></div>
    <button @click="showHomeViewwFunction" class="contact-button">Speak With Us Now</button>
</div>
<div v-if="showHomeVieww">
    <div class="rectangle-container">
        <h1>{{ title }}</h1>
    </div>
    <ContactForm />
</div>

<div class="about-container">
    <div class="about-content">
        <div class="text-section">
            <h2 class="sub-heading">About Us</h2>
            <p class="large-text">{{ about }}</p>
        </div>
        <div class="image-section">
            <img src="https://www.kryderlaw.com/wp-content/uploads/2023/01/Carpentersville-Personal-Injury-Lawyer.jpg" alt="Descriptive text">
        </div>
    </div>
</div>
        <div
         class="attorneys-container">
            <h2>Make Your Issue is Our Issue</h2>
            <p>{{ attorneys }}</p>
    </div>
    <div class="practice-areas-title">
    <h2>Practice Areas</h2>
</div>
    <div class="tabs-container">
        <div class="tabs">
            <div class="tab" 
     v-for="(tab, index) in tabs" 
     :key="index" 
     @click="selectedTabIndex = index" 
     :class="{ 'active-tab': selectedTabIndex === index }">{{ tab.name }}
</div>

                <div class="tab-content">
    <img :src="selectedTab.src" :alt="selectedTab.name" class="tab-image">
    <div class="tab-description">
        <p>{{ selectedTab.description }}</p>
    </div>
</div>

        </div>
    </div>
<div class="credentials">
    <h2 class="sub-heading">Ashly Van Earl</h2>
   
    <h2 class="sub-heading">Credentials</h2>
    <p class="large-text">{{ ashly.desc }}</p>
    
</div>
        <h2 class="sub-heading">Client Reviews</h2>
        <img src="https://lh4.googleusercontent.com/GqX0masriPRiAoXB7g4V61J7MtJMMlIOteKfT6N_0-Hjn6pjuPYdEgL44eThOzQs8nrgZmjVIa6RVSYrflJhI4D4h38n0AMsW-UzlEyGJQQiWEcADdxxfll7r7JtuOBGhA=w1280" class="CENy8b" role="img">

    <div class="info">
            <p><strong>Office Hours :</strong> {{ hours }}</p>
            <p><strong>Address :</strong> {{ address }}</p>
            <p><strong>Phone :</strong> {{ phone }}</p>
            <p><strong>Email :</strong> {{ email }}</p>
            <p><strong>Facebook :</strong> {{ facebook }}</p>
            <div class="spanish-section">
            <h2>{{ spanish }}</h2>
            </div>
            <p><strong>Email en Español :</strong> {{ emailSpanish }}</p>        
            <p><strong>Facebook Español :</strong> {{ facebookSpanish }}</p>
           
        </div>
        
</template>
<script>
 
 import ContactForm from './ContactForm.vue';
export default {
    name: 'HomeView',
    components:{
     ContactForm
    },
    
    props: {
        show: {
            type: Boolean,
            required: true
        }
    },
  
    data() {
        return {
             selectedTabIndex: 0,
             tabs: [
    { 
        name: 'Common Law', 
        src: 'https://divorcebroward.com/wp-content/uploads/2019/08/common-law.jpg', 
        description: "Common law is a body of unwritten laws based on precedents established by the courts. It's the foundation for many legal systems worldwide, offering broad coverage of various legal matters. These legal principles evolve with society, allowing laws to adapt to changing circumstances. The principles of common law serve as a guide for judges and provide a framework for decision-making in court cases."
    },
    { 
        name: 'Criminal Law', 
        src: 'https://edwardslawofficepc.com/wp-content/uploads/2019/05/criminal-law-plaque-ontable-with-gavel.jpg', 
        description: 'Criminal law refers to the body of laws that define criminal offenses and prescribe punishments for their violations. These laws are designed to regulate social conduct and maintain the peace and security of society. They set out the rights and responsibilities of individuals and provide the framework for the processes involved in the prosecution of criminal offenders. The ultimate aim is to deter individuals from committing crimes, thereby ensuring public safety.' 
    },
    { 
        name: 'Business Law', 
        src: 'https://www.broadviewsolicitorsllp.com/wp-content/uploads/2023/01/Business-Law-BVSLLP.jpg', 
        description: 'Business law, also known as commercial law, refers to the set of laws that govern business and commercial transactions. It includes a wide array of topics such as contracts, the law of corporations and other business organizations, securities law, intellectual property, anti-trust, secured transactions, and commercial paper. It also encompasses newer fields like health, the internet, and competition laws.' 
    },
    { 
        name: 'Immigration Law', 
        src: 'https://www.attorneygeneral.gov/wp-content/uploads/2020/03/CR_immigration_LG.jpg', 
        description: "Immigration law includes the rules established by a country's government which dictate who can enter the country and for how long. It also lays out the legal obligations, rights, and duties of aliens in that country. Immigration laws vary from country to country, as well as according to the political climate of the times, as sentiments may sway between leniency and stringency."
    },
    { 
    name: 'Personal Injury Law', 
    src: 'https://swartzlaw.com/wp-content/uploads/2021/12/Personal-Injury-Law-Firm-1.jpg', 
    description: "Personal injury law involves cases where an individual's body, mind, or emotions are injured, usually due to someone else's negligence or carelessness. It includes wrongful death or situations where an injury proves fatal. Personal injury law allows an injured person to go to civil court and get a legal remedy (damages) for all losses stemming from an accident or other incident."
}

],
           title:"Speak With Us Now",
           showHomeVieww:false,
            imagePath: require('../assets/web.png'),
            name: 'ImageOverlay',
            showForm: false,
            about: 'The Earl Law Firm is an esteemed legal practice recognized for proficiently addressing the needs of both businesses and individuals. Our comprehensive expertise extends to a wide range of legal matters, including personal injury, criminal defense, family law, and immigration law. We have a rich history of successfully advocating for our clients rights, navigating through complex legal landscapes, and delivering resolution for a myriad of claims. Our commitment to legal excellence is unwavering, and our resolve in championing for justice, unwearied.',
            hours: '9:00 AM – 5:00 PM Monday - Friday',
            address: '9422 Common St. Suite 1. Baton Rouge, LA 70809',
            phone: '(225)761-9456',
            email: 'ashly@earllawfirm.com',
            emailSpanish: 'marycruz@earllawfirm.com',
            spanish: 'Se Habla Español',
            facebook: 'Facebook.com/EARLLAWFIRM',
            facebookSpanish: 'Facebook.com/ABOGADOASHLYEARL',
            attorneys: 'Unlike large law firms, where you may never meet or talk to the primary attorney working on your case, at The Earl Law Firm you can count on personal one on one attention from our attorneys. This is because as a small firm, quality relationships with our clients is important in keeping the company running smoothly.',
            ashly: {
                name: 'Ashly Van Earl',
                desc: '2004 Graduating class of Southern University Law School With 19 years of experience, Ashly has a large breadth of legal knowledge covering subjects such as Civil litigation, Criminal Defense law, Business & Breach of contract, Successions, and Immigration Law.',
            }
        }
    },
    computed: {
  selectedTab: function () {
    return this.tabs[this.selectedTabIndex];
  }
},

    mounted(){
    this.currentShow = this.show;
    this.selectedTab = this.tabs[0];
    this.selectedTabIndex = 0;
},
    methods: {
        handleFormSubmit(data) {
            // send data to server
            console.log(data);
            fetch('https://example.com/api/contact', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(data)
            });
        
        
        },
        navigateToPracticeAreas() {
            this.$emit('showPracticeAreas');
            console.log("blah");
            
            console.log(this.show);
  },
  showHomeViewwFunction(){
    this.showHomeVieww = !this.showHomeVieww;
  }
    },
}
</script>

<style scoped>

    .info {
        background-color:#001f3f ;  /* Navy blue color */
        color: #fff;  /* You may want to change the text color to white for better contrast */
        padding: 60px;
        margin-bottom: 60px;
        border-radius: 5px;
        font-family: 'Arial', sans-serif;
    }

   
    .sub-heading {
        color: #1a3d50;
        font-size: 2em;
        margin-top: 20px;
        margin-bottom: 10px;
    }

    p {
        line-height: 1.6;
    }

    .contact-button {
        background-color: #1a3d50;
        color: #fff;
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
        cursor: pointer;
    }

    .credentials {
    margin-top: 0;
    background-color: #f2f2f2;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 5px;
    position: relative;
    overflow: hidden; /* Hide the lines outside of the div */
    font-family: 'Arial', sans-serif;
}

  .sub-heading {
    color: #001f3f;
    font-family: 'Arial', sans-serif;
  }

  .about-container {
    background-color: #f2f2f2;
    padding: 20px;
    margin-bottom: 0px; /* Reduce the bottom margin */
    border-radius: 5px;
    font-family: 'Arial', sans-serif;
}

.sub-heading {
    color: #001f3f;
    font-family: 'Arial', sans-serif;
}

.about-content {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    position: relative;
    font-family: 'Arial', sans-serif;
}

.about-content::after {
    content: '';
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 3px;
    background-color: #001f3f;
    font-family: 'Arial', sans-serif;
}

.text-section, .image-section {
    padding: 20px;
    width: 45%;
    font-family: 'Arial', sans-serif;
}

.text-section {
    display: flex;
    flex-direction: column;
    align-items: center; /* Center items vertically in the text-section */
    font-family: 'Arial', sans-serif;
}

.image-section img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: center;
    font-family: 'Arial', sans-serif;
}

/* Responsive design */

    .spanish-section {
        background-color:  #001f3f;
        font-family: 'Fiesta', cursive;
    }

    .spanish-section h2 {
        font-size: 2em;
        font-family: 'Arial', sans-serif;
    }

    .spanish-section p {
        font-size: 1.2em;
        font-family: 'Arial', sans-serif;
    }
    .attorneys-container {
    background-color: #001f3f;  /* Dark navy color */
    color: #fff; /* White color for the text */
    padding: 20px;
    font-size: 2em;
    margin-top: 0px; /* Reduce the top margin */
    margin-bottom: 20px;
    border-radius: 5px;
    font-family: 'Arial', sans-serif;
    }

    .attorneys-container h2 {
        position: relative;
        padding-bottom: 10px;
        color: #fff; /* White color for the heading */
        font-family: 'Arial', sans-serif;
    }

    .attorneys-container h2::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 0;
        height: 2px;
        width: 100%;
        background: linear-gradient(to right, rgba(255, 255, 255, 0), #fff, rgba(255, 255, 255, 0));
        font-family: 'Arial', sans-serif;
    }

    .attorneys-container p {
        color: #fff; /* White color for the text */
        font-size: 24px; /* Increase size as per requirement */
        max-width: 700px;
        margin: 0 auto;
        font-family: 'Arial', sans-serif;
    }
    
   

.top-container {
    position: relative;
    height: 70vh;
    min-height: 700px;
    font-family: 'Arial', sans-serif;
}

.image-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    font-family: 'Arial', sans-serif;
}

.top-image {
    background-image: url('../assets/web.png');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    opacity: 0.8;
    z-index: 2;
}

.bottom-image {
    background-image: url('https://www.travellens.co/content/images/2022/04/Baton-Rouge.jpg');
    background-size: cover;
    background-position: 20% center;
    filter: url(#blur);
  
  
}


.contact-button {
    position: absolute;
    bottom: 20px;
    left: 50%; /* to center the button */
    transform: translateX(-50%); /* to perfectly center the button */
    padding: 10px 20px;
    background-color: #ffcc00; 
    color: #333; 
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    z-index: 10; 
}

.contact-button:hover {
    background-color: #e6b800;
}
 
.rectangle-container {
    width: 100vw; /* This will make the rectangle the width of the viewport */
    background-color: #333; /* This sets the background color to black */
    padding: 10px;
    box-sizing: border-box; /* This ensures that padding and border are included in the element's total width and height */
    display: flex;
    justify-content: center; /* This centers the title horizontally */
    align-items: center; /* This centers the title vertically */
    height: 100px; /* You can adjust the height as needed */
    font-family: 'Arial', sans-serif;
}

.rectangle-container h1 {
    color: #fff; /* This makes the title color white */
    font-size: 2em; /* This makes the title larger */
    font-family: 'Arial', sans-serif;
}


.tabs {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly; /* This rule distributes all children equally along the row */
    flex-wrap: wrap; /* This rule allows the tabs to wrap into multiple lines if necessary */
    font-family: 'Arial', sans-serif;
}



.tab:not(.active):hover {
    font-family: 'Arial', sans-serif;
    color: #1a3d50;
}


.tab {
      cursor: pointer;
      padding: 10px 15px;
      color: #000;
      text-decoration: none;
      transition: color 0.3s;
      font-family: 'Arial', sans-serif;
  }

  .tab:hover {
      color: #777;
      font-family: 'Arial', sans-serif;
  }

  .active-tab {
      border-bottom: 3px solid #001f3f;
      font-family: 'Arial', sans-serif;
  }



  .tab-content {
    display: flex;
    justify-content: space-between;
    width: 100vw; /* Make it as wide as the screen */
    max-width: 100%; /* Ensure it does not exceed its parent container */
    border-radius: 5px;
    margin-top: 20px;
    font-family: 'Arial', sans-serif;
}

.tab-image {
    width: 45%; /* Make the image fill up 75% of the left half of the page */
    height: auto;
    object-fit: cover; /* This will ensure that your image maintains its aspect ratio */
    border-radius: 5px;
    margin-right: 18px;
}

.tab-description {
    width: 50%; /* Balance out the remaining width */
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    font-size: 20px;
    font-family: 'Arial', sans-serif;
}



.tabs-container {
    background-color: #f2f2f2;  /* Light Silver color */
    color: #001f3f; /* Dark navy color for the text */
    padding: 20px;
    font-size: 2em;
    border-radius: 5px;
    font-family: 'Arial', sans-serif;
}

.practice-areas-title h2 {
    font-size: 2em;
    color: #001f3f;
    margin-top: 20px;
    font-family: 'Arial', sans-serif;
}
</style>
