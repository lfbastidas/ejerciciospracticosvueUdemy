<template>
<div>
    <base-card> 
    <the-button @click="setSelectTab('store-resources')" :mode="storedResButtonMode" > Stored Resources </the-button>
    <the-button @click="setSelectTab('add-resource')" :mode="addResButtonMode"> Add Resources</the-button>
    </base-card>
    <keep-alive>
    <component :is="selectTab"> </component>
    </keep-alive>
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
        resources: this.storedResources,
        addResource: this.addResource
    }
},

   methods: {
        setSelectTab(tab){
            this.selectTab=tab;     
                    // lo hago para cambiar de pestañas
        },
        addResource (title, description, url) {
            const newResource =  {
                id: new Date().toISOString(),
                tittle:title,
                description: description,
                link: url
            }
            this.storedResources.unshift(newResource);
            this.selectTab = 'store-resources'

        }
    }
}
</script>