<template>
<div>
    <base-card> 
    <the-button @click="setSelectTab('store-resources')" :mode="storedResButtonMode" > Stored Resources </the-button>
    <the-button @click="setSelectTab('add-resource')" :mode="addResButtonMode"> Add Resources</the-button>
    </base-card>
    <component :is="selectTab"> </component>
</div>
</template>

<script>
import StoreResources from './StoreResources.vue';
import AddResource from './AddResource.vue'


export default {
     components: {
                        StoreResources, AddResource},
    data () {
        return {
            selectTab: 'store-resources'    //lo hago para cambiar de pestañas
        ,

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
    },
    computed: {
        storedResButtonMode(){
            return  this.selectTab==='store-resources'? null:'flat'
        },
        addResButtonMode(){
            return this.selectTab ==='add-resource'? null: 'flat'
        }
    },


provide() {
    return {
        resources: this.storedResources
    }
},






    
    methods: {
        setSelectTab(tab){
            this.selectTab=tab;     
                    // lo hago para cambiar de pestañas
        }
    }
}
</script>