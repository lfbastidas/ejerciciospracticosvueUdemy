<template>
<ul>
   <learning-resource
   v-for="obj in storedResources" 
   :key="obj.id"
   :tittle="obj.tittle"
   :description="obj.description"
   :link="obj.link"
   >
   </learning-resource>
</ul>
</template>


<script>

import LearningResource from './components/learning-resources/LearningResource.vue'
export default {
 components: {'learning-resource': LearningResource},


    data (){
        return {
            storedResources: [
                {
                    id: 'official-guide',
                    tittle: 'official guide',
                    description: 'The official Vue.js documentation',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'google-guide',
                    tittle: 'google guide',
                    description: 'The official google documentation',
                    link: 'https://google.org'
                }
            ]
        }
    }
}
</script>