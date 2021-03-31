<template>
<div>
    <h2> Manage Goals </h2>
    <input type="text" v-model="enterdValue"> 
    <h3> {{enterdValue}} </h3>
    <button @click="setGoal"> Set Goal </button>
    <teleport to="body">
    <error-alert v-if="inputIsInvalid">
        <h2> Input is invalid </h2>
        <p> Please enter at least a few characteres... </p>
        <button @click="confirmError"> Okay </button>
   </error-alert>
   </teleport>
</div>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue'
export default {
    components: {
    ErrorAlert
    },
    data(){
        return {
            enterdValue:'',
            inputIsInvalid: false
        }
    },
    methods:{
        setGoal(){
            if (this.enterdValue ===''){
               // alert('Input must not be empty')
               this.inputIsInvalid=true;
            }
        },
        confirmError(){
            this.inputIsInvalid=false;
        }
    }
}
</script>