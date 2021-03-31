<template>
<li>
   <div>
     <header>
       <h3>    {{tittle}} </h3>
       <button> Delete </button>
     </header>
    </div>
  <p> {{description}}</p>
   <nav> 
     <a :href="link"> View Resource </a>
   </nav>
</li>
</template>

<script>
export default {
    props: ['id','tittle', 'description', 'link']
}
</script>