<template>
  <v-app>
    <v-container fluid class="pa-0">
      <v-img
        :src="imageSrc"
        :height="isMobile ? '250px' : '350px'"
        :contain="isMobile"
        cover
        class="responsive-img"
      ></v-img>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      imageSrc: 'https://resized-images.autoconf.com.br/1920x450/filters:format(webp)/site/592/f84ccffb-edcf-462c-9124-f2079a64cdea.jpg',
      isMobile: false,
    };
  },
  mounted() {
    this.checkScreenSize();
    window.addEventListener('resize', this.checkScreenSize);
  },
  methods: {
    checkScreenSize() {
      this.isMobile = window.innerWidth < 768;
    }
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkScreenSize);
  }
};
</script>

<style scoped>
.responsive-img {
  width: 100%;  /* Faz a imagem ocupar toda a largura */
  max-width: 100%;
  object-fit: cover; /* Ajusta a imagem sem distorcer */
}
</style>