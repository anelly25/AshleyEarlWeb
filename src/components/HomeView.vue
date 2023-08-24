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
            <h2>Make Your Issue Our Issue</h2>
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
    <h2 class="sub-heading">Ashly Van arl</h2>
   
    <h2 class="sub-heading">Credentials</h2>
    <p class="large-text">{{ ashly.desc }}</p>
    
</div>

    <div class="info">
            <p><strong>Office Hours :</strong> {{ hours }}</p>
            <p><strong>Address :</strong> {{ address }}</p>
            <p><strong>Phone :</strong> {{ phone }}</p>
            <p><strong>Email :</strong> {{ email }}</p>
            <p><strong>Facebook :</strong> <a :href="facebook" target="_blank">{{ facebook }}</a></p>
            <div class="spanish-section">
            <h2>{{ spanish }}</h2>
            </div>
            <p><strong>Email en Español :</strong> {{ emailSpanish }}</p>        
            <p><strong>Facebook Español :</strong> <a :href="facebookSpanish" target="_blank">{{ facebookSpanish }}</a></p>
           
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
    name: 'Contract Law', 
    src: 'https://media.istockphoto.com/id/1130476273/photo/signing-the-agreement-in-the-contract.jpg?s=612x612&w=0&k=20&c=NlA-eL5ELryzYJCG4HMRgliVG78gdYgw1bYyI_y9UdE=', 
    description: "Contract law pertains to the creation and enforcement of agreements between parties. It provides a legal framework that ensures promises made in contracts are honored, setting out the rights and obligations of each party. This body of law governs various aspects like validity, enforceability, and breach of contracts. The central aim is to ensure fairness and predictability in commercial and everyday transactions, ensuring that all parties fulfill their respective promises."
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
            facebook: 'https://Facebook.com/EARLLAWFIRM',
facebookSpanish: 'https://Facebook.com/ABOGADOASHLYEARL',
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
    background-color:#001f3f;
    color: #fff;
    padding: 5vw;
    margin-bottom: 5vw;
    font-family: 'Arial', sans-serif;
}

.sub-heading {
    color: #1a3d50;
    font-size: 2vw;
    margin-top: 2vw;
    margin-bottom: 1vw;
}

p {
    line-height: 1.6;
}

.contact-button {
    background-color: #1a3d50;
    color: #fff;
    border: none;
    padding: 1vw 2vw;
    border-radius: 5px;
    cursor: pointer;
}

.credentials {
    margin-top: 0;
    background-color: #f2f2f2;
    padding: 2vw;
    margin-bottom: 2vw;
    border-radius: 5px;
    position: relative;
    overflow: hidden;
    font-family: 'Arial', sans-serif;
}

.about-container {
    background-color: #f2f2f2;
    padding: 2vw;
    margin-bottom: 0;
    border-radius: 5px;
    font-family: 'Arial', sans-serif;
}

.about-content {
    display: flex;
    justify-content: space-between;
    gap: 2vw;
    position: relative;
    font-family: 'Arial', sans-serif;
}

.about-content::after {
    content: '';
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 0.3vw;
    background-color: #001f3f;
    font-family: 'Arial', sans-serif;
}

/* rest of your styles adapted in a similar fashion */


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
    background-color: #001f3f; /* Dark navy color */
    color: #fff; /* White color for the text */
    padding: 1.25em; /* 20px assuming base font size is 16px */
    font-size: 1em;
    margin-top: 0; /* Reduce the top margin */
    margin-bottom: 1.25em; /* 20px assuming base font size is 16px */
    font-family: 'Arial', sans-serif;
}

.attorneys-container h2 {
    position: relative;
    padding-bottom: 1.5em; /* 10px assuming base font size is 16px */
    color: #fff; /* White color for the heading */
    font-family: 'Arial', sans-serif;
}

.attorneys-container h2::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    height: .2em; /* 2px assuming base font size is 16px */
    width: 100%;
    background: linear-gradient(to right, rgba(255, 255, 255, 0), #f9d403, rgba(255, 255, 255, 0));
    font-family: 'Arial', sans-serif;
}

.attorneys-container p {
    color: #fff; /* White color for the text */
    font-size: 1.5em; /* 24px assuming base font size is 16px */
    max-width: 43.75em; /* 700px assuming base font size is 16px */
    margin: 0 auto;
    font-family: 'Arial', sans-serif;
}

   

.top-container {
    position: relative;
    height: 50vh; /* This is already a relative unit */
    min-height: 43.75em; /* 700px assuming base font size is 16px */
    font-family: 'Arial', sans-serif;
}

.image-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%; /* This is already a relative unit */
    height: 100%; /* This is already a relative unit */
    font-family: 'Arial', sans-serif;
}

.top-image {
    background-image: url('../assets/FullLogo.jpg');
    background-size: contain; /* This is relative to its container */
    background-repeat: no-repeat;
    background-position: center; /* This is relative to its container */
    opacity: 0.8; /* This is already a relative unit */
    z-index: 2; /* z-index doesn't have a relative unit equivalent, it's unitless */
}

.bottom-image {
    background-image: url('https://www.travellens.co/content/images/2022/04/Baton-Rouge.jpg');
    background-size: cover; /* This is relative to its container */
    background-position: 20% center; /* This is already a relative unit */
    filter: url(#blur); /* Filters don't have a relative unit equivalent */
}


.contact-button {
    position: absolute;
    bottom: 1.25em; /* 20px */
    left: 50%; /* to center the button */
    transform: translateX(-50%); /* to perfectly center the button */
    padding: 0.625em 1.25em; /* 10px 20px */
    background-color: #ffcc00;
    color: #333;
    border: none;
    border-radius: 0.3125em; /* 5px */
    font-size: 1.5em; /* 16px */
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
    padding: 0.625em; /* 10px */
    box-sizing: border-box; /* This ensures that padding and border are included in the element's total width and height */
    display: flex;
    justify-content: center; /* This centers the title horizontally */
    align-items: center; /* This centers the title vertically */
    height: 6.25em; /* 100px */
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
    justify-content: space-evenly;
    flex-wrap: wrap;
    font-family: 'Arial', sans-serif;
}

.tab:not(.active):hover {
    font-family: 'Arial', sans-serif;
    color: #1a3d50;
}

.tab {
    cursor: pointer;
    padding: 0.625em 0.9375em; /* 10px 15px */
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
    border-bottom: 0.1875em solid #001f3f; /* 3px */
    font-family: 'Arial', sans-serif;
}

.tab-content {
    display: flex;
    justify-content: space-between;
    width: 100vw;
    max-width: 100%;
    border-radius: 0.3125em; /* 5px */
    margin-top: 1.25em; /* 20px */
    font-family: 'Arial', sans-serif;
}

.tab-image {
    width: 40%; /* Relative to the width of the parent element */
    height: 75%; /* Relative to the height of the parent element */
    object-fit: cover;
    margin-top: 1em;
    margin-left: 1.5em;
    border: 0.125em solid gold; /* Add this line for gold border */
}


.tab-description {
    width: 50%; /* Increased from 50% */
    padding: 2em; /* 20px */
    display: flex;
    flex-direction: column;
    justify-content: center;
    font-size: .9em; /* Decreased from 1.25em */
    font-family: 'Arial', sans-serif;
}

.tabs-container {
    background-color: #f2f2f2;
    color: #001f3f;
    padding: 1em; /* Relative to the font-size of the element (1em = 100%) */
    font-size: 1.25em; /* Relative to the parent element's font size */
    /* Relative to the border box of the element, max(5% of width, 5% of height) */
    font-family: 'Arial', sans-serif;
    border-top: 0.125em solid rgb(14, 10, 95); /* 0.125em is relative to the font-size of the element */
    border-bottom: 0.125em solid rgb(35, 21, 118); /* Add this line for gold border */
}



.practice-areas-title h2 {
    font-size: 2em;
    color: #001f3f;
    margin-top: 1.25em; /* 20px */
    font-family: 'Arial', sans-serif;
}
@media screen and (max-width: 480px) {
    .top-container {
        height: 40vh;
        min-height: 20em;
    }

    .top-image{
      
        width:100%;
    }
    .bottom-image {
        background-size: cover;
        background-position: center;
    }

    .contact-button {
        bottom: 0.625em;  /* reduce button position for smaller screens */
        padding: 0.3em 0.6em;  /* reduce button padding for smaller screens */
        font-size: 0.8em;  /* reduce button font size for smaller screens */
    }
    .about-content {
        flex-direction: column;
    }

    .about-content::after {
        content: none;
    }

    .text-section, .image-section {
        padding: 10px;
        width: 100%;
    }

    .text-section {
        text-align: center;
    }

    .tabs {
        flex-direction: column;
    }

    .tab:not(.active):hover {
        font-size: 0.8em; /* Decrease the font-size */
    }

    .tab {
        padding: 0.2em 0.3em; /* Decrease the padding */
        font-size: 1em; /* Decrease the font size */
        margin-left: 4em;
    }

    .active-tab {
        border-bottom: 0.05em solid #001f3f; /* Decrease the border thickness */
    }

    .tab-content {
        flex-direction: column; /* Change flex direction */
        margin-top: 0.5em; /* Decrease the top margin */
        height: 40vh; /* Adjust to fit within tabs-container's max-height */
    }

    .tab-image {
        width: 100%; /* Image takes full width */
        height: 40%; /* Adjust to fit within tab-content's height */
      /* No need for right margin in smaller screens */
        border: 0.05em solid gold; /* Decrease the border thickness */
    }

    .tab-description {
        width: 100%; /* Description takes full width */
        font-size: 1em; /* Decrease the font size */
    }

    .tabs-container {
        background-color: #f2f2f2;
        color: #001f3f;
        padding: 0.3em; /* Decreased from 0.5em */
        font-size: 0.8em; /* Decreased from 1em */
        font-family: 'Arial', sans-serif;
        border-top: 0.05em solid rgb(14, 10, 95);
        border-bottom: 0.05em solid rgb(35, 21, 118);
        max-width: 90%; /* The container will take only 90% of the width of its parent element */
        margin: auto; /* To center the container */
        max-height: 100vh; /* Adjust as per your needs */
        overflow: auto; /* If the content overflows, a scrollbar will appear */
        margin-left: 1em;
    }


    .practice-areas-title h2 {
        font-size: 1.5em; /* Decrease the font size */
        margin-top: 0.625em; /* Decrease the top margin */
    }

    .attorneys-container {
    padding: 1.25em; /* 20px assuming base font size is 16px */
    font-size: 1em;
    margin-top: 0; /* Reduce the top margin */
    margin-bottom: 1.25em; /* 20px assuming base font size is 16px */
    border-radius: 0.3125em; /* 5px assuming base font size is 16px */
 
}

.attorneys-container h2 {
    padding-bottom: 1.5em; /* 10px assuming base font size is 16px */ 
}

.attorneys-container h2::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    height: .2em; /* 2px assuming base font size is 16px */
    width: 100%;
}

.attorneys-container p {  
    font-size: 1em; /* 24px assuming base font size is 16px */
    max-width: 43.75em; /* 700px assuming base font size is 16px */
    margin: 0 auto;;
}

.info {
    padding: 12vw;
    margin-bottom: 15vw;
    font-family: 'Arial', sans-serif;
    font-size:.7em;
}

.sub-heading { 
    font-size: 5vw;  
}

.credentials {
   font-size:.75em;
}

}

</style>
