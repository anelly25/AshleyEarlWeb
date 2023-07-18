<template>   
     <div v-if = "show" >       
        <div class="language-notification">
            <p>We speak Spanis, see below. | Hablamos español, vea abajo.</p>
        </div>
        <div class="top-container">               
        
       </div>
       <div class="about-container">
    <h2 class="sub-heading">About Us</h2>
    <div class="about-content">
        <div class="text-section">
            <p class="large-text">{{ about }}</p>
        </div>
        <div class="image-section">
            <img src="https://www.kryderlaw.com/wp-content/uploads/2023/01/Carpentersville-Personal-Injury-Lawyer.jpg" alt="Descriptive text">
        </div>
    </div>
</div>
        <div class="attorneys-container">
            <h2>Make Your Issue is Our Issue</h2>
            <p>{{ attorneys }}</p>
    </div>
    <div class="practice-areas-container">
    <h2 class="sub-heading">Practice Areas</h2>
    <div class="images-container">
        <div class="top-row">
            <img class="practice-area-img" src="https://www.attorneygeneral.gov/wp-content/uploads/2020/03/CR_immigration_LG.jpg" alt="Practice Area 1">
            <img class="practice-area-img" src="https://edwardslawofficepc.com/wp-content/uploads/2019/05/criminal-law-plaque-ontable-with-gavel.jpg" alt="Practice Area 2">
            <img class="practice-area-img" src="https://swartzlaw.com/wp-content/uploads/2021/12/Personal-Injury-Law-Firm-1.jpg" alt="Practice Area 3">
        </div>
        <div class="bottom-row">
            <img class="practice-area-img" src="https://www.broadviewsolicitorsllp.com/wp-content/uploads/2023/01/Business-Law-BVSLLP.jpg" alt="Practice Area 4">
            <img class="practice-area-img" src="https://divorcebroward.com/wp-content/uploads/2019/08/common-law.jpg" alt="Practice Area 5">
        </div>
    </div>
</div>
<div class="credentials">
    <h2 class="sub-heading">Ashly Van Earl</h2>
   <img src="data:image/jpeg;base64,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" alt="Description of image" class="credentials-img">
    <h2 class="sub-heading">Credentials</h2>
    <p class="large-text">{{ ashly.desc }}</p>
    <div class="fading-line-1"></div>
    <div class="fading-line-2"></div>
</div>
        <h2 class="sub-heading">Client Reviews</h2>
        <img src="https://lh4.googleusercontent.com/GqX0masriPRiAoXB7g4V61J7MtJMMlIOteKfT6N_0-Hjn6pjuPYdEgL44eThOzQs8nrgZmjVIa6RVSYrflJhI4D4h38n0AMsW-UzlEyGJQQiWEcADdxxfll7r7JtuOBGhA=w1280" class="CENy8b" role="img">

    <div class="info">
            <p><strong>Office Hours :</strong> {{ hours }}</p>
            <p><strong>Address :</strong> {{ address }}</p>
            <p><strong>Phone :</strong> {{ phone }}</p>
            <p><strong>Email :</strong> {{ email }}</p>
            <p><strong>Facebook :</strong> {{ facebook }}</p>
        </div>
        <div class="spanish-section">
            <h2>{{ spanish }}</h2>
            <p><strong>Email en Español :</strong> {{ emailSpanish }}</p>
            <p><strong>Facebook Español :</strong> {{ facebookSpanish }}</p>
        </div>  
        </div>
</template>
<script>


export default {
    name: 'HomeView',
    components: {
        
    },
    props: {
        show: {
            type: Boolean,
            required: true
        }
    },
    data() {
        return {
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
        }
    },
}
</script>

<style scoped>
    .container {
        max-width: 1100px;
        margin: 0 auto;
        padding: 20px;
        font-family: 'Times New Roman', serif;
        color: #333;
    }
 
    .header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 120px;
        color: #fff;
        background-size: cover;
    }
   

    .title {
    color: #fff;
    font-size: 2.5em;
    text-align: left;
    margin-bottom: 20px;
    padding: 15px;
    background: rgba(0,0,0,0.5);
    backdrop-filter: blur(10px);
    border: 2px solid white; /* Add this line */
}
    .info {
        background-color: #1a3d50;  /* Navy blue color */
        color: #fff;  /* You may want to change the text color to white for better contrast */
        padding: 20px;
        margin-bottom: 20px;
        border-radius: 5px;
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

    .contact-button:hover {
        background-color: #144a6c;
    }
   
    .contact-container {
    padding: 20px;
    max-width: 600px;
    height: 120px; /* Add this line to set an explicit height */
    border: 2px solid #1a3d50;
    border-radius: 5px;
    text-align: center;
    margin: 90px auto 50px auto;
    background-color: rgba(26, 61, 80, 0.5);
    backdrop-filter: blur(10px);
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
.contact-container h2 {
    margin-bottom: 10px;
    color: #fff; /* Make the heading color white */
}

.credentials {
    background-color: #f2f2f2;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 5px;
    position: relative;
    overflow: hidden; /* Hide the lines outside of the div */
  }

  .sub-heading {
    color: #001f3f;
  }

  .fading-line-1, .fading-line-2 {
    position: absolute;
    top: 0;
    left: 0;
    height: 200%; /* Make the lines longer */
    width: 200%; /* Make the lines longer */
    pointer-events: none;  /* So the lines do not interfere with clicking */
  }

  .fading-line-1 {
    background: linear-gradient(45deg, transparent 10%, rgba(0, 0, 0, 0.8) 50%, transparent 90%);
    transform: translateY(-50%); /* Offset the line */
  }

  .fading-line-2 {
    background: linear-gradient(-45deg, transparent 10%, rgba(0, 0, 0, 0.8) 50%, transparent 90%);
    transform: translateY(50%); /* Offset the line */
  }
    .about-container {
    background-color: #f2f2f2;
    border-left: 5px solid #001f3f;
    border-right: 5px solid #001f3f;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 5px;
}

.sub-heading {
    color: #001f3f;
}

.about-content {
    display: flex;
    justify-content: space-between;
    gap: 20px;
    position: relative;
}

.about-content::after {
    content: '';
    position: absolute;
    left: 50%;
    top: 0;
    bottom: 0;
    width: 3px;
    background-color: #001f3f;
}

.text-section, .image-section {
    padding: 20px;
    width: 45%;
}

.image-section img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* The image should cover its content box, possibly clipping the image */
    object-position: center; /* The image will be centered within its content box */
}
    .spanish-section {
        border: 2px solid #1a3d50;
        border-radius: 5px;
        background-color: #f8b24f;
        padding: 20px;
        margin-bottom: 20px;
        font-family: 'Fiesta', cursive;
    }

    .spanish-section h2 {
        font-size: 2em;
    }

    .spanish-section p {
        font-size: 1.2em;
    }
    .language-notification {
        position: absolute;
        top: 51px; /* Adjust this value according to the height of your navigation bar */
        right: 0;
        padding: 10px;
        background-color: #ffcc00; /* Yellow color for better visibility */
        z-index: 999; /* To ensure the notification is on top */
        font-family: Arial, sans-serif; /* Choose your preferred font */
        font-size: 0.8em; /* Adjust this value to change the size of your text */
    }
    

    .images-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    border: 2px solid navy;
}

.top-row, .bottom-row {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.practice-area-img {
    width: 300px;
    height: 200px;
    object-fit: cover;
    margin: 5px;
    transition: filter 0.3s ease;
}

.practice-area-img:hover {
    filter: brightness(50%);
    cursor: pointer;
}

@media screen and (max-width: 600px) {
    .practice-area-img {
        width: 100%;
    }
}


.attorneys-container {
    background-color: #1a3d50; /* Navy color from your page */
    color: #fff; /* White color for the text */
    padding: 20px;
    font-size: 2em;
    margin-bottom: 20px;
    border-radius: 5px;
}

.attorneys-container h2 {
    position: relative;
    padding-bottom: 10px;
}

.attorneys-container h2::after {
    content: "";
    position: absolute;
    bottom: 0;
    left: 0;
    height: 2px;
    width: 100%;
    background: linear-gradient(to right, rgba(255, 255, 255, 0), #fff, rgba(255, 255, 255, 0));
}

.attorneys-container p {
    color: #fff;/* Navy color from your page */
    font-size: 24px; /* Increase size as per requirement */
    max-width: 700px; 
    margin: 0 auto
}
    
.top-container {
    background-image: url('../assets/web.png');
    background-size: cover;
    background-position: center;
    height: 70vh;
    min-height: 700px;
}
.credentials-img {
    width: 50%;  /* Adjust as necessary */
    height: auto; /* This will maintain the aspect ratio of the image */
}
.image-container {
  position: relative;
  width: 500px;
  height: 500px;
}

.background-image {
  width: 100%;
  height: 100%;
}


</style>