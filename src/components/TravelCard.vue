<template>
  <div class="card">
    <section class="parallax"></section>
    <section class="text">¡Hola amigos!</section>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.card {
  display: grid;
  grid-template-rows: 1fr 1fr;
  justify-content: center;
  align-items: center;
  width: 700px;
  height: 100%;
  border: 2px solid whitesmoke;
  overflow: auto;  /* Esto permite que el contenido se desplace */
}

.parallax {
  min-height: 400px;
  min-width: 700px;
  background-image: url(../assets/landsphoto.jfif);
  background-position: center;
  background-attachment: fixed;  /* Aquí agregamos esta propiedad */
  background-size: contain;  /* Para asegurar que la imagen cubra toda el área */
}

.text {
  padding: 1.2rem;
  text-align: justify;
  width: 100%;
  height: 100%;
}
</style>
