<template>
  <div class="portfolio">
    <!-- Header, Navbar and Social Medias -->
    <div :class="[isDark ? 'header' : 'header light_mode']">
      <div class="name_switch">
        <p>Edomiyas Temesgen</p>
        <label class="switch">
          <input type="checkbox" @click="isDark = !isDark">
          <span class="slider round"></span>
        </label>
      </div>
      <div class="navbar">
        <nav>
          <a href="">Home</a>
          <a href="#AboutMe">About me</a>
          <a href="#ccc">CCC</a>
          <a href="#Projects">Projets</a>
          <a href="#Contact">Contact me</a>
        </nav>
      </div>
      <div class="social_media">
        <div class="linkedin">
          <a href="https://www.linkedin.com/in/edomiyas-temesgen-16ba01173" target="_blank" v-if="isDark"><img src="../assets/socialmedia/logo-linkedin.png" alt="linkedin"/> LinkedIn</a>
          <a href="https://www.linkedin.com/in/edomiyas-temesgen-16ba01173" target="_blank" v-if="!isDark"><img src="../assets/socialmedia/logo-linkedin-noir.png" alt="linkedin"/> LinkedIn</a>
        </div>
        <div class="github">
          <a href="https://github.com/etemesgen" target="_blank" v-if="isDark"><img src="../assets/socialmedia/logo-github.png" alt="github"/> Github</a>
          <a href="https://github.com/etemesgen" target="_blank" v-if="!isDark"><img src="../assets/socialmedia/logo-github-noir.png" alt="github"/> Github</a>
        </div>
      </div>
    </div>

    <!-- Home page -->
    <div class="home_container">
      <div class="home">
        <div class="intro">
          <p id="role">Front-end / Mobile Developer</p>
          <h1>If you never failed, </h1>
          <h1 id="second_line">you never tried anything new.</h1>
          <p id="third_line">I love creating interfaces, coding and pretty much learning new things. I aspire to become an expert in mobile developement !</p>

          <a href="" id="chat_button" class="underline">LET'S CHAT !</a>
        </div>
        <div class="technos_overview">
          <img src="../assets/tech/technos_overview.png" alt="tech">
        </div>
      </div>

      <a href="#AboutMe" class="scroll"><img src="../assets/buttons/scroll.png" alt="scroll"></a>
    </div>

    <!-- About page -->
    <div class="about_me" id="AboutMe">
      <div class="left_section">
        <TechCard title="Front-end" :images="frontEnd"/>
          <br>
        <TechCard title="Back-end" :images="backEnd"/>
          <br>
        <TechCard title="Database" :images="database"/>
          <br>
        <TechCard title="Version control" :images="versionControl"/>
          <br>
      </div>
      <div class="right_section">
        <h1>Hello ! I'm Edomiyas Temesgen</h1>
        <p id="quote">“First, solve the problem. Then, write the code.” – John Johnson</p>
        <p id="description">That’s what coding teaches me every day. Before even thinking to code, we have to be a problem solver. Being a third year software engineering student with an internship, i work to succeed using my passion for living.</p>
        <div class="concept">
          <img src="../assets/concept/problem-solving.png" alt="problem-solving">
          <img src="../assets/concept/right-arrow.png">
          <img src="../assets/concept/web-programming.png" alt="code">
        </div>
        <div class="mobile_uiux">
          <TechCard id="mobile" title="Mobile Developement" :images="mobileDevelopement"/>
            <br>
          <TechCard id="uiux" title="UI/UX Design" :images="uiUxDesign"/>
        </div>
      </div>
    </div>

    <!-- CCC page -->
    <div class="ccc" id="ccc">
      <div class="definition">
        <h2 id="curiosity" class="underline underline_curiosity">Curiosity</h2>
        <p>is what got me into IT development.</p>
        <h2 id="creativity" class="underline underline_creativity">Creativity</h2>
        <p>is what motivates me in my developer adventure.</p>
        <h2 id="concept" class="underline underline_concept">Concept</h2>
        <p>is what fascinates me about IT development.</p>
      </div>
      <div class="chart">
        <img src="../assets/chart/ccc_chart.png" alt="ccc_chart">
      </div>
    </div>

    <!-- Projects page -->
    <div class="projects_container" id="Projects">
      <a href="https://github.com/etemesgen?tab=repositories" target="_blank" id="all_projects">All projects</a>
      <hr>
      <div class="projects">
        <ProjectCard/>
        <ProjectCard/>
        <ProjectCard/>
        <ProjectCard/>
      </div>
    </div>

    <!-- Contact page -->
    <div class="contact" id="Contact">
      <div class="title">
        <h1>Start by <span class="underline">saying hi</span></h1>
        <br>
      </div>
      <div class="contact_form">
        <form action="">
          <input type="text" name="name" id="name" placeholder="Name" required>
            <br>
          <input type="text" name="mail" id="mail" placeholder="Mail" required>
            <br>
          <textarea name="message" id="" cols="30" rows="10" placeholder="Message..." required></textarea>
            <br>
          <button type="submit">Send</button>
        </form>
        <div class="infos">
          <p>Information</p>
          <br>
          <h2>temesgen.edomiyas@yahoo.com</h2>
          <br>
          <div class="nav_logo">
            <div class="nav">
              <a href="#">Home</a> 
              <a href="#AboutMe">About me</a>
              <a href="#ccc">CCC</a>
              <a href="#Projects">Projects</a>
              <a href="#">Contact me</a>
            </div>
            <div class="logo">
              <img src="../assets/logo.png" alt="logo">
            </div>
          </div>
        </div>
      </div>

      <div class="footer">
        <div class="social_medias">
          <a href="https://www.linkedin.com/in/edomiyas-temesgen-16ba01173" target="_blank"><img src="../assets/socialmedia/logo-linkedin.png" alt="linkedin"> &nbsp;</a>
          <a href="https://github.com/etemesgen" target="_blank"><img src="../assets/socialmedia/logo-github.png" alt="github"></a>
        </div>
        <p>2022. Made with 💚 by Edomiyas</p>
        <a href="#"><img id="arrow_to_top" src="../assets/buttons/arrow_to_top.png" alt="arrow_to_top"></a>
      </div>
    </div>
  </div>  
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  data(){
    return{
      isDark: true,
      frontEnd: [
        require("../assets/tech/vue.png"),
        require("../assets/tech/nuxt.png"),
        require("../assets/tech/sass.png"),
        require("../assets/tech/ts.png")
      ],
      backEnd: [
        require("../assets/tech/nodejs.png"),
        require("../assets/tech/express.png"),
      ],
      database: [
        require("../assets/tech/mongodb.png"),
        require("../assets/tech/postgresql.png"),
      ],
      versionControl: [
        require("../assets/tech/git.png")
      ],
      mobileDevelopement: [
        require("../assets/tech/react-native.png"),
        require("../assets/tech/ionic.png"),
      ],
      uiUxDesign: [
        require("../assets/tech/figma.png")
      ],
    }
  }
})
</script>

<style lang="scss">
@import url('http://fonts.cdnfonts.com/css/rockwell-nova');
@import '../theme/header.scss';
@import '../theme/home.scss';
@import '../theme/about_me.scss';
@import '../theme/ccc.scss';
@import '../theme/projects.scss';
@import '../theme/contact.scss';

:root{
  font-family: 'Rockwell Nova', sans-serif;
  scroll-behavior: smooth;
}

body{
  background-color: #4E5A6B;
}

.light_mode{
  background-color: #FFFFFF;

  p ,a{
    color: #222222;
  }
}


</style>