<template>
<div>
<the-header tittle="RememberME"></the-header>

<the-resource> </the-resource>
</div>
</template>


<script>

//import StoreResources from './components/learning-resources/StoreResources';
import TheHeader  from './components/Layouts/TheHeader.vue';
import TheResource from './components/learning-resources/TheResource.vue';
export default {
 components: {
               'the-header':TheHeader,
               'the-resource': TheResource},


    
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>