<template>
<store-resources :resources="storedResources"> </store-resources>
</template>


<script>

import StoreResources from './components/learning-resources/StoreResources'
export default {
 components: {'store-resources': StoreResources},


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