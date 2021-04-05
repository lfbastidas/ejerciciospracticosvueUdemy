<template>
    <ul>
   <learning-resource
   v-for="obj in resources" 
   :key="obj.id"
   :tittle="obj.tittle"
   :description="obj.description"
   :link="obj.link"
   >
   </learning-resource>
</ul>
</template>


<script>
import LearningResource from './LearningResource.vue'

export default {
    components:{
        LearningResource
       
    },
    inject : ['resources']
}
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>