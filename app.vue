<template>
  <div id="app" class="cv-container">
    <header class="header">
      <h1>{{ name }}</h1>
      <p class="title">{{ title }}</p>
      <p class="contact">{{ email }}</p>
      <p class="contact">{{ phone }}</p>
    </header>
    
    <section class="section">
      <h2>Profile</h2>
      <p>{{ profile }}</p>
    </section>

    <section class="section">
      <h2>Experience</h2>
      <ul>
        <li v-for="(job, index) in experiences" :key="index">
          <h3>{{ job.position }} - {{ job.company }}</h3>
          <p>{{ job.period }}</p>
          <p>{{ job.description }}</p>
        </li>
      </ul>
    </section>

    <section class="section">
      <h2>Education</h2>
      <ul>
        <li v-for="(education, index) in educations" :key="index">
          <h3>{{ education.degree }} - {{ education.institution }}</h3>
          <p>{{ education.period }}</p>
        </li>
      </ul>
    </section>

    <section class="section">
      <h2>Skills</h2>
      <ul class="skills-list">
        <li v-for="(skill, index) in skills" :key="index">{{ skill }}</li>
      </ul>
    </section>

    <section class="section">
      <h2>Portfolio</h2>
      <div class="portfolio">
        <div 
          class="portfolio-item" 
          v-for="(project, index) in portfolio" 
          :key="index"
        >
          <h3>{{ project.name }}</h3>
          <p>{{ project.description }}</p>
          <a :href="project.link" target="_blank">View Project</a>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "I am Nur Husnil Khotimah Harahap",
      title: "Student",
      email: "husnilharahap85@gmail.com",
      phone: "082267985866",
      profile: "A student of Information Technology who is currently learning and has a deep interest in web-based technology development through various academic and personal projects.",
      experiences: [
        {
          position: "App Design Project",
          company: "ColleGo",
          description: "Designed and developed a mobile application for college using Figma App, focusing on user interface and user experience."
        },
      ],
      educations: [
        {
          degree: "Senior High School",
          institution: "Darul Mursyid Senior High School",
          period: "2021 - 2023"
        },
        {
          degree: "Diploma in Information Technology",
          institution: "Brawijaya University",
          period: "2023 - Completed"
        }
      ],
      skills: ["JavaScript", "Vue.js", "HTML", "CSS", "UI/UX"],
      portfolio: [
        {
          name: "UI DESIGNEER",
          description: "A personal app designed with Figma to showcase my UI design skills and projects, including interface designs and prototypes.",
          link: "https://www.figma.com/design/L3IvXz6aCWxeCHn9irfCVJ/UAS-UI-UX?node-id=0-1&t=P6849m3atznEw3HG-1"
        },
      ]
    };
  }
};
</script>

<style scoped>
.cv-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #F8F4E3; /* Mengubah warna latar belakang menjadi putih tulang */
  border: 1px solid #e0e0e0;
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
  border-radius: 10px;
}

.header {
  text-align: center;
  padding: 20px;
  background: rgba(255, 255, 255, 0.8);
  color: #8B4513; /* Mengubah warna font menjadi coklat coconut */
  border-radius: 10px 10px 0 0;
}

.header h1 {
  margin: 0;
  font-size: 2.5em;
  font-weight: bold; /* Menebalkan teks */
  text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.2); /* Menambahkan bayangan pada teks */
}

.header .title {
  margin: 5px 0;
  font-size: 1.5em; /* Mengubah ukuran font judul */
  font-weight: 500; /* Sedikit menebalkan teks */
}

.header .contact {
  margin: 2px 0;
  font-size: 1.2em; /* Mengubah ukuran font untuk email dan telepon */
}

.section {
  margin: 20px 0;
}

.section h2 {
  margin-bottom: 10px;
  color: #8B4513; /* Mengubah warna judul section menjadi coklat coconut */
  border-bottom: 2px solid #8B4513; /* Mengubah warna garis bawah menjadi coklat coconut */
  display: inline-block;
}

.section ul {
  list-style-type: none;
  padding: 0;
}

.section ul li {
  margin: 10px 0;
  padding: 15px;
  border: 1px solid #e0e0e0;
  background-color: #f9f9f9;
  border-radius: 5px;
  transition: transform 0.3s, box-shadow 0.3s;
}

.section ul li:hover {
  transform: translateY(-5px);
  box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.1);
  color: #8B4513; /* Mengubah warna font saat hover menjadi coklat coconut */
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.skills-list li {
  background-color: #87674c;
  color: #1b1717;
  padding: 5px 10px;
  border-radius: 5px;
  transition: background-color 0.3s;
}

.skills-list li:hover {
  background-color: #87674c;
}

.portfolio {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 15px;
}

.portfolio-item {
  border: 1px solid #e0e0e0;
  padding: 15px;
  background-color: #fff;
  border-radius: 8px;
  text-align: center;
  transition: transform 0.3s, box-shadow 0.3s;
}

.portfolio-item:hover {
  transform: translateY(-5px);
  box-shadow: 0px 4px 20px rgba(0, 0, 0, 0.1);
}

.portfolio-item h3 {
  margin: 0 0 5px;
  color: #87674c;
}

.portfolio-item p {
  color: #555;
}

.portfolio-item a {
  display: inline-block;
  margin-top: 10px;
  padding: 8px 15px;
  color: #fff;
  background-color: #87674c;
  text-decoration: none;
  border-radius: 20px;
  transition: background-color 0.3s;
}

.portfolio-item a:hover {
  background-color: #87674c;
}
</style>