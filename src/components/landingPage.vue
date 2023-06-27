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
      <section class="content" id="sobre">
        <div class="container">
          <h2>Sobre</h2>
          <figure class="profile">
            <img :src="profileImage" alt="Leonardo Car">
          </figure>
          <p class="big-text">{{ aboutText }}</p>
          <p class="big-text">{{ aboutSkills }}</p>
          <p class="big-text">{{ aboutSkills2 }}</p>
        </div>
      </section>
      <section class="content" id="projetos">
        <div class="container">
        <h2>Experiências Profissionais</h2>
          <div>
            <ul>
              <li v-for="item in jobHistory" :key="item.id" class="li-experiences">
                <p style="font-weight: bold;">
                {{ item.title }}
                </p>
                <p>
                  {{ item.period }}
                </p>
                <p>
                  {{ item.description }}
                </p>
              </li>
            </ul>
          </div>
        </div>
      </section>
      <section class="content" id="skills">
        <div class="container">
        <h2>Skills</h2>
          <div>
            <ul>
              <li v-for="item in skills" :key="item.id">
                <p>
                {{ item.title }}
                </p>
              </li>
            </ul>
          </div>
        </div>
      </section>
      <section class="content" id="cursos">
        <div class="container">
        <h2>Cursos</h2>
          <div>
            <ul>
              <li v-for="item in courses" :key="item.id" class="li-experiences">
                <p>
                {{ item.title }} - {{ item.school }}
                </p>
                  <a :href="generateLink(item.credential)">
                    Ver Certificado 
                  </a>
              </li>
            </ul>
          </div>
        </div>
      </section>
      <section class="content" id="cursos">
        <div class="container">
          <h2>Formação Acadêmica</h2>
          <div>
            <ul>
              <li v-for="item in academicFormation" :key="item.id" class="li-experiences">
                <p>
                  {{ item.course }} - {{ item.school }}
                </p>
                <p>
                  {{ item.date }}
                </p>
              </li>
            </ul>
          </div>
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

        skills: [
          { id: "1", title: "React"},
          { id: "2", title: "Vue.js"},
          { id: "3", title: "Javascript"},
          { id: "4", title: "Typescript"},
          { id: "5", title: "Postgres"},
          { id: "6", title: "Hasura Graphql"},
          { id: "7", title: "Git e Gitflow"},
          { id: "8", title: "Prisma"},
          { id: "9", title: "Inglês Fluente"}
        ],

        jobHistory: [
          {
            id: "1",
            title: "Desenvolvedor Fullstack - Codee.tech",
            period: "Out. 2021 - Atual",
            description: "Entrei na empresa Codee.tech como desenvolvedor júnior e comecei a trabalhar com a ferramenta React no frontend e Hasura GraphQL com Typescript no backend. Fui encarregado de desenvolver um projeto completo de base fullstack. Por um bom tempo trabalhei sozinho no projeto, mas também tive a oportunidade de contar com a ajuda de outros desenvolvedores em momentos específicos. Durante essa experiência, aprendi a lidar com a gestão de projetos, bem como a importância da comunicação clara e transparente com o cliente. Também tive a chance de trabalhar em outros dois projetos da empresa em alguns períodos."
          },
          {
            id: "2",
            title: "Desenvolvedor Frontend - GPr Sistemas",
            period: "Fev. 2021 - Jul. 2021",
            description: "Durante meu período na GPR Sistemas, desenvolvi habilidades em JavaScript e React, aprendendo conceitos cruciais de segurança de software, como Token JWT e SSH, além de práticas seguras no desenvolvimento de aplicações web. Me aprofundei em React, utilizando e compreendendo o uso de state, props e React Router.",
          },
          {
            id: "3",
            title: "Desenvolvedor Web - CasBrasil Conexão Farma",
            period: "Fev. 2019 - Fev. 2021",
            description: "Entrei como estagiário na empresa, durante o período de graduação, estava concluindo o Técnico de informática, onde tive uma breve introdução sobre programação. Durante o período em atividade dentro da empresa, fui contratado de estagiário para desenvolvedor. Desenvolvendo fullstack com Django(Framework Python), tanto para frontend quanto para backend, participei de dois projetos, um e-commerce e um sistema de convênios. Durante meu tempo na empresa aprendi muita coisa referente ao mundo de desenvolvimento, sendo elas GIT, Scrum, Conceitos de UI/UX e o principal, o Desenvolvimento com Python. Além disso, também aprendi como trabalhar com o Docker para a criação de ambientes de desenvolvimento e produção."
          },
          {
            id: "4",
            title: "Estagio -  Técnico em sistemas de informática - CasBrasil Conexão Farma",
            period: "Out. 2018 - Dez. 2018",
            description: "-"
          }
        ],

        courses: [
          {
            id: "1",
            credential: "7269bbe7-5706-424b-a68b-18be2090b834",
            title: "REACT: FUNCTION COMPONENTS, UMA ABORDAGEM MODERNA",
            school: "Alura"
          },
          {
            id: "2",
            credential: "8e5cae51-81e9-411d-9b99-0b509259153b",
            title: "DOCKER: CRIANDO CONTAINERS SEM DOR DE CABEÇA",
            school: "Alura",
          },
          {
            id: "3",
            credential: "7ae3c9b5-1c50-485b-bb03-9337c41fe020",
            title: "JAVASCRIPT: PROGRAMANDO NA LINGUAGEM DA WEB",
            school: "Alura",
          },
          {
            id: "4",
            credential: "ea7d9e1d-d956-4e1c-9b13-dd0629a6cd33",
            title: "Rest com NodeJS: API com Express e MySQL",
            school: "Alura",
          }
        ],

        academicFormation: [
          {
            id: "1",
            school: "Colégio Politécnico Bento Quirino",
            course: "Ensino Médio",
            date: "2016-2018"
          },
          {
            id: "2",
            school: "Colégio Politécnico Bento Quirino",
            course: "Técnico em Informática",
            date: "2016-2018"
          },
          {
            id: "3",
            school: "Colégio Paes Júnior",
            course: "Ensino Fundamental II",
            date: "2014-2015"
          },
          {
            id: "4",
            school: "Colégio Múltiplo",
            course: "Ensino Fundamental I e II",
            date: "2003-2013"
          },
        ],

        projects: [
          { title: "Project 1", image: "path/to/project1-image.jpg" },
          { title: "Project 2", image: "path/to/project2-image.jpg" },
          { title: "Project 3", image: "path/to/project3-image.jpg" }
        ],
        githubLink: "https://github.com/Lccas",
        linkedinLink: "https://www.linkedin.com/in/leonardocarvalho133/",
        instagramLink: "https://www.instagram.com/leoboakk/",
        baseUrl: 'https://cursos.alura.com.br/certificate/',
      };
    },

    methods: {
      generateLink(url) {
        return this.baseUrl + url;
      },
    },

  };
  </script>
  
  <style>
    @import '@/styles/styles.scss'
  </style>
  