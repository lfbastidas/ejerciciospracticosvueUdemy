<template>
<base-dialog v-if="inputIsInvalid" title="Invalid Input" @close="confirmError">

<template #default> 
  <p> Unfortunately, at least one input value is invalid. </p>
  <p> Please check all inputs </p>
</template>

<template #actions>
  <the-button @click="confirmError"> Okay </the-button>
</template>


 </base-dialog>
    <base-card> 
    <form @submit.prevent="submitData">
        <div class="form-control">
            <label for="title" > Title </label>
            <input id="title" name="title" type="text" v-model="titleInput">
        </div>
        <div class="form-control">
            <label for="description" > Description </label>
            <textarea id="description" name="descirption" rows="3" v-model="descInput"> </textarea>
            
        </div>

        <div class="form-control">
            <label for="link" > Link</label>
            <input id="link" name="link" type="url" v-model="linkInput">
        </div>

        <div class="form-control">
            <the-button type="submit"> Add Resource </the-button>
        </div>
        
    </form>
    
    </base-card>
</template>
<script>
export default {
  inject:['addResource']
,  data () {
    return {
     titleInput:'',
     descInput:"",
     linkInput:"",
     inputIsInvalid:false
    }
  },
  methods:  {
  submitData(){

const enterdTittle =  this.titleInput;
const enterdDesc = this.descInput;
const enterdLink = this.linkInput;
  if(enterdTittle.trim()==='' || enterdDesc.trim()==='' || enterdLink.trim()===''){
    this.inputIsInvalid = true;
return;
  }
this.addResource(enterdTittle, enterdDesc, enterdLink)
  },
  confirmError(){
    this.inputIsInvalid = false;
  }
  }
}
</script>

<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>