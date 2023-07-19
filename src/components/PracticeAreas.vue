<template>
    <div class="practice-areas">
      <div class="area" v-for="area in areas" :key="area.title">
        <img :src="area.image" :alt="area.title" class="area-image">
        <h2 class="area-title">{{ area.title }}</h2>
        <p class="area-description">{{ area.description1 }}</p>
        <p class="area-description">{{ area.description2 }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'PracticeAreas',
    data() {
      return {
        areas: [
  {
    title: 'Immigration Law',
    image: 'path/to/immigration-law-image.jpg',
    description1: 'Our team of dedicated immigration attorneys is experienced in all aspects of immigration law. From assisting clients in obtaining visas, to handling complex deportation cases, our firm has the expertise necessary to navigate the often complicated U.S. immigration system.',
    description2: 'We believe in the importance of family reunification, the right to seek employment opportunities, and the ability to seek refuge from persecution. We are committed to providing exceptional service and results-oriented legal representation to clients from all over the world.',
  },
  {
    title: 'Criminal Law',
    image: 'path/to/criminal-law-image.jpg',
    description1: 'Our criminal law practice is dedicated to protecting the rights and interests of those accused of crimes. We handle a wide range of criminal cases, including DUI/DWI, drug offenses, theft crimes, violent crimes, white collar crimes, and more.',
    description2: 'We believe in the presumption of innocence and the right to a fair trial. Our experienced criminal defense attorneys are dedicated to providing aggressive, effective defense strategies tailored to the unique circumstances of each case.',
  },
  {
    title: 'Personal Injury Law',
    image: 'path/to/personal-injury-law-image.jpg',
    description1: 'Our personal injury lawyers are dedicated to helping individuals who have been injured due to the negligence or recklessness of others. We handle a variety of personal injury cases, including auto accidents, slip and fall accidents, medical malpractice, product liability, and wrongful death.',
    description2: 'We strive to obtain maximum compensation for our clients to cover medical expenses, loss of income, pain and suffering, and other damages. Our team provides compassionate and personalized legal representation, guiding our clients through each step of the legal process.',
  },
  {
    title: 'Business Law',
    image: 'path/to/business-law-image.jpg',
    description1: 'Our business law practice serves entrepreneurs, small businesses, and large corporations alike. We handle a broad spectrum of business-related issues, including business formation, contract drafting and negotiation, intellectual property protection, mergers and acquisitions, and dispute resolution.',
    description2: 'Our goal is to provide practical legal solutions that support our clients’ business objectives. We offer strategic advice and representation in both transactional matters and litigation, helping businesses navigate the complexities of the legal landscape.',
  },
  {
    title: 'Common Law',
    image: 'path/to/common-law-image.jpg',
    description1: 'Our common law practice covers a wide range of legal areas that impact individuals and businesses. This includes property law, contract law, tort law, and more. We aim to provide comprehensive legal advice and representation to protect our clients’ rights and interests.',
    description2: 'Our firm values strong client relationships, professionalism, and ethical practice. We are committed to understanding our clients’ needs and providing legal solutions that are both efficient and effective.',
  },
],
      };
    },
  };
  </script>
  
  
  <style scoped>
.practice-areas {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  background-color: #001f3f;
  padding: 20px;
  padding-bottom: 100px; /* add padding bottom to ensure some visible background under the boxes */
  min-height: 100vh; /* Ensure full height of the viewport is used */
}

.area {
  flex: 1 0 300px;
  margin: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
  background-color: white;
  max-width: 800px;
}

.area-image {
  width: 100%;
  height: auto;
}

.area-title {
  font-size: 20px;
  font-weight: bold;
  margin-top: 20px;
}

.area-description {
  font-size: 16px;
  margin-top: 10px;
}

@media (max-width: 768px) {
  .practice-areas {
    flex-direction: column;
    align-items: center;
  }

  .area {
    flex-basis: 100%;
    max-width: 100%;
  }
}
</style>