<template>
  <div class="text-md-center">
    <v-avatar
      color="grey lighten-4"
      size="120"
    >
      <img
        :src="publicPath('/img/avatar.png')"
        alt="Christian Pfarher"
      >
    </v-avatar>
  </div>
</template>

<script>
export default { name: 'Avatar' }
</script>

<style scoped>

</style>
