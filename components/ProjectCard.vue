<template>
    <div class="projectCard">
      <div class="left_section">
        <img src="../assets/projects/images.jpeg" alt="tip_calculator">
      </div>
      <div class="right_section">
        <div class="title_desc">
          <h2>Tip Calculator app</h2>
          <p>To help servers or restaurants to calculate tip.</p>
        </div>
        <div class="techs_links">
          <p>HTML, CSS, JS</p>
          <div>
            <a href=""><img src="../assets/project_links/github_link.png" alt="github_link"></a>
            <a href=""><img src="../assets/project_links/online_link.png" alt="online_link"></a>
          </div>
        </div>
      </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'ProjectCard',
  props: {
    image: { type : String },
    title: { type : String },
    description: { type : String },
    technologies: { type : Array },
    onlineLink: { type: URL },
    githubLink: { type: URL }  
  }
})
</script>

<style lang="scss" scoped>
.projectCard{
  border-radius: 10px;
  display: flex;
  width: 35rem;
  height: 11.2rem;
  margin-top: 70px;
  transition: all .2s ease-in-out; 

  .left_section{
    img{
      border-radius: 10px 0 0 10px;
      width: 260px;
      height: 179px;
    }
  }

  .right_section{
    flex-direction: column;
    border: 1px solid #81f9b9;
    border-radius: 0 10px 10px 0;
  }

  h2{
    color: #81f9b9;
  }

  .title_desc{
    padding-left: 20px;
  }

  .techs_links{
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    background-color: #a7ffd07a;
    height: 47px;
    border-radius: 0 0 10px 0;

    p{
      position: relative;
      left: 20px;
    }

    a{
      padding-right: 20px;
      position: relative;
      top: 5px;
    }
  }
}

.projectCard:hover{
  transform: scale(1.1);
}

</style>