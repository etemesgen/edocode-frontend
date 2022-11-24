<template>
  <div class="techCard">
    <p>{{ title }}</p>
    <div class="images">
      <div v-for="(image, i) in images" :key="i">
        <img :src="image">
      </div>
    </div> 
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'TechCard',
  props: {
    title: { type : String },
    images: { type : Array }
  }
})
</script>

<style lang="scss" scoped>

.techCard{
  background-color: #576374;
  padding: 10px 25px 10px 20px;
  border-radius: 5px;
  transition: all .2s ease-in-out; 
  
  p{
    text-align: left;
  }

  .images{
    display: flex;
    gap: 40px;
  }
}

.techCard:hover{
  transform: scale(1.1);
}
</style>