<template>
    <div id="app">
      <header>
        <nav class="menu">
          <ul class="container">
            <li><a href="#sobre">Sobre</a></li>
            <li><a href="#projetos">Projetos</a></li>
            <li><a href="#contato">Contato</a></li>
          </ul>
        </nav>
        <div>
          <h1 class="site-title">{{ siteTitle }}</h1>
          <h2 class="site-subtitle">{{ siteSubtitle }}</h2>
        </div>
      </header>
      <section class="sobre" id="sobre">
        <h2>Sobre</h2>
        <figure class="profile">
          <img :src="profileImage" alt="Leonardo Car">
        </figure>
        <p class="big-text">{{ aboutText }}</p>
        <p class="big-text">{{ aboutSkills }}</p>
        <p class="big-text">{{ aboutSkills2 }}</p>
      </section>
      <section class="portfolio" id="projetos">
        <h2>Projetos</h2>
        <div class="grid">
          <figure v-for="(project, index) in projects" :key="index">
            <img class="img-portfolio" :src="project.image" :alt="project.title">
            <figcaption>{{ project.title }}</figcaption>
          </figure>
        </div>
      </section>
      <section id="contato">
        <footer>
          <div class="footer">
            <a :href="githubLink">
              <i class="fab fa-github fa-2x"></i>
            </a>
            <a :href="linkedinLink">
              <i class="fab fa-linkedin fa-2x"></i>
            </a>
            <a :href="instagramLink">
              <i class="fab fa-instagram fa-2x"></i>
            </a>
          </div>
        </footer>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        siteTitle: "Leonardo Carvalho",
        siteSubtitle: "Fullstack Developer",
        profileImage: require("@/assets/profile.jpeg"),
        aboutText: "Olá! Meu nome é Leonardo Carvalho e sou um desenvolvedor FullStack apaixonado por transformar ideias em realidade através da programação. Com 23 anos de idade, tenho uma sólida formação técnica e uma paixão por aprender e evoluir constantemente.",
        aboutSkills: "Minha proficiência técnica abrange um conjunto de tecnologias amplamente utilizadas no desenvolvimento web, como React, Vue, Hasura GraphQL, Prisma, Git e Docker",
        aboutSkills2: "Além disso, tenho fluência em inglês, o que me permite trabalhar em projetos internacionais e colaborar com equipes multiculturais. Tenho boas habilidades de comunicação, o que facilita a compreensão e a expressão de ideias.",


        projects: [
          { title: "Project 1", image: "path/to/project1-image.jpg" },
          { title: "Project 2", image: "path/to/project2-image.jpg" },
          { title: "Project 3", image: "path/to/project3-image.jpg" }
        ],
        githubLink: "https://github.com/Lccas",
        linkedinLink: "https://www.linkedin.com/in/leonardocarvalho133/",
        instagramLink: "https://www.instagram.com/leoboakk/"
      };
    }
  };
  </script>
  
  <style>
    @import '@/styles/styles.scss'
  </style>
  