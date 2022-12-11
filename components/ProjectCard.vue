<template>
    <div class="projectCard">
      <div class="left_section">
        <img src="../assets/projects/images.jpeg" alt="tip_calculator">
      </div>
      <div class="right_section">
        <div class="title_desc">
          <h2>{{ this.title }}</h2>
          <p>{{ this.description }}</p>
        </div>
        <div class="techs_links">
          <p v-for="(tech, i) in this.technologies" :key="i">{{ tech }}</p>
          <div>
            <a :href="this.githubLink" target="_blank"><img src="../assets/project_links/github_link.png" alt="github_link"></a>
            <a :href="this.onlineLink" target="_blank"><img src="../assets/project_links/online_link.png" alt="online_link"></a>
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
    onlineLink: { type: String },
    githubLink: { type: String }  
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
      height: 100%;
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
    height: 60%;
  }

  .techs_links{
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    background-color: #a7ffd07a;
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

@media only screen and (max-width: 768px) {
  .projectCard{
    flex-direction: column;
    width: 20rem;
    height: auto;

    .left_section{
      img{
        border: 1px solid #81f9b9;
        border-radius: 10px 10px 0 0;
        width: 100%;
      }
    }

    .right_section{
      border-radius: 0 0 10px 10px;
      position: relative;
      bottom: 5px;

      h2{
        font-size: 1.2rem;
      }
    }
  }
}
</style>