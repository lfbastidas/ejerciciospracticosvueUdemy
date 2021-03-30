<template>
  <section>
    <base-card>
    <div>
      <h3>{{ fullName }}</h3>
      <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
    </div>
    <p>{{ infoText }}</p>
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