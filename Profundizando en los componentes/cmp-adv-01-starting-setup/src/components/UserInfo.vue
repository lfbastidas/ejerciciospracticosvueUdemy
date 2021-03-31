<template>
  <section>
    <base-card>
    <template v-slot:header> <!--  sirve para el otro slot llamado header en la plantilla BaseCard-->
      <h3>{{ fullName }}</h3>
      <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
    </template>
    <template v-slot:default>
    <p>{{ infoText }}</p>
    </template>
    </base-card>
  </section>

</template>

<script>
export default {
  props: ['fullName', 'infoText', 'role'],
};
</script>
<!-- Estilos solo para este componente -->
<style scoped>


</style>