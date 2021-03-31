<template>
  <div>
    <the-header></the-header>
    <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <course-goals>
      <template v-slot:default="slotProps">  <!-- slot Props me vincula las propiedades utilizadas en el slot usado en el componente CourseGoals -->
      <h2>{{slotProps.item}}</h2>
      <p>{{slotProps['another-prop']}} </p>
      </template > 
    </course-goals>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import UserInfo from './components/UserInfo.vue';
import BadgeList from './components/BadgeList.vue';
import CourseGoals from './components/CourseGoals.vue';

export default {
  components: {
   'the-header': TheHeader,
   'user-info': UserInfo,
   'badge-list': BadgeList,
   'course-goals': CourseGoals

  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
};
</script>
<!-- Aqui defino los estilos q usara la aplicacion a nivel global -->
<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>