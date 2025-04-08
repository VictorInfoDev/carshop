<template>
  <v-app>
    <v-container fluid class="pa-0">
      <v-img
      :src="imageSrcTop"
      :height="isMobile ? '30vw' : '27vw'"
      cover
      class="banner-img"
      />
    </v-container>
    <v-container fluid class="mt-15 pa-15 pb-5">
    <v-row dense class="">
      <v-col
        v-for="n in 4" :key="n"
        cols="12" sm="12" md="6" lg="3"
        class="pa-10"
      >
        <v-card class="hover-grow-card" ripple style="min-height: 300px; min-width: 250px; cursor: pointer;" outlined>
          <v-img
            src="https://img.olx.com.br/images/86/867542134491516.webp"
            height="250"
          ></v-img>
          <v-card-title style="font-weight: bold; white-space: nowrap;">FERRARI CALIFORNIA</v-card-title>
          <v-card-subtitle style="text-align: left;">4.3 V8 GASOLINA F1-DCT</v-card-subtitle>
          <v-card-text style="text-align: left;" class="">
          <v-row>
            <v-col>
            <v-row dense class="d-flex flex-wrap">
              <v-col
                v-for="(info, i) in infos"
                :key="i"
                class="d-flex align-center"
                style="flex: 0 0 auto; min-width: 200px;"
              >
                <v-icon class="mr-2">{{ info.icon }}</v-icon>
                <span style="font-weight: bold; white-space: nowrap;">
                  {{ info.text }}
                </span>
              </v-col>
            </v-row>
            </v-col>
            <v-col color="" class="" style="font-weight: bold; white-space: nowrap;">
              <v-icon large class="mr-2" color="red">mdi-horse-variant-fast</v-icon><span><h1>365 cv</h1></span>
            </v-col>
          </v-row> 
          </v-card-text>
          <v-card-title><h2>R$ 2.000.000</h2></v-card-title>
          <v-btn
              :ripple="false"
              fab
              elevation="0"
              top
              left
              color="transparent"
              absolute
              ><img src="https://logodownload.org/wp-content/uploads/2017/05/ferrari-logo-1-1.png" alt="Ícone" style="width: 60px; height: 80px;" />
          </v-btn>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
  <v-container fluid class="pa-0">
      <v-img
      :src="imageSrcRoro"
      :height="isMobile ? '30vw' : '27vw'"
      cover
      class="banner-img"
      style="box-shadow: none;"
      />
    </v-container>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      imageSrcTop: require('@/assets/banner grande home top.png'),
      imageSrcRoro: require('@/assets/roro banner.png'),
      isMobile: false,
      infos: [
      { icon: 'mdi-road-variant', text: '223.000 km' },
      { icon: 'mdi-calendar-blank', text: '2019/2020' },
      { icon: 'mdi-gas-station', text: 'Gasolina' },
    ],
    };
  },
  mounted() {
    this.checkScreenSize();
    window.addEventListener('resize', this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkScreenSize);
  },
  methods: {
    checkScreenSize() {
      this.isMobile = window.innerWidth < 768;
    }
  }
};
</script>

<style scoped>
.banner-img {
  width: 100%;     /* Sempre toda a largura */
  object-fit: cover; /* Corta pra ficar certinha no espaço */
}
.banner-img {
  width: 100%;
  object-fit: contain;
  background-color: #000; /* se ainda estiver usando */
  box-shadow: 0px 8px 16px rgba(0, 0.1, 0.2, 0.5); /* sombra personalizada */
}
.hover-grow-card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  box-shadow: none;
}

.hover-grow-card:hover {
  transform: scale(1.05); /* aumenta 5% */
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3); /* adiciona sombra bonita */
}
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@400;700&display=swap');

* {
  font-family: 'Kanit', sans-serif;
}
</style>