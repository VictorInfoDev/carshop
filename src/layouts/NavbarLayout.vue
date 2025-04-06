<template>
    <v-app>
        <v-app-bar app class="black" elevation="15" dark>
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" class="d-md-none color-logo"></v-app-bar-nav-icon>
            <v-img src="https://i.pinimg.com/originals/09/97/c5/0997c5f5d2390d34202e8dd8261db18e.jpg" max-height="120" max-width="120" class="ml-5"></v-img>
            <v-toolbar-title class="ml-2 color-logo oleo-script-bold"><h2>Luxury Cars</h2></v-toolbar-title>
            <v-spacer></v-spacer>
            <div class="d-none d-md-flex">
                <v-btn text tile class="color-logo">Estoque</v-btn>
                <v-btn text tile class="color-logo">Venda seu carro</v-btn>
                <v-btn text tile class="color-logo">Financie</v-btn>
                <v-btn text tile class="color-logo">Sobre</v-btn>
            </div>
            <v-navigation-drawer
            v-model="drawer"
            absolute
            temporary
            app
            class="black"
            >
            <v-list>
                <v-list-item-group
                v-model="group"
                active-class="text--accent-4"
                >
                <v-list-item v-for="(item, i) in menuItems" :key="i">
                    <v-list-item-title class="color-logo">{{ item }}</v-list-item-title>
                </v-list-item>
                <v-divider></v-divider>
                <v-list-item @click="drawer = false">
                    <v-list-item-title class="orange--text">Fechar</v-list-item-title>
                </v-list-item>
                </v-list-item-group>
            </v-list>
            </v-navigation-drawer>
        </v-app-bar>
        <v-main>
            <router-view></router-view>
        </v-main>
    </v-app>
</template>

<script>
export default {
  data() {
    return {
      drawer: false, // Estado do menu lateral
      menuItems: ["Estoque", "Venda seu carro", "Financie", "Sobre"],
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oleo+Script:wght@400;700&display=swap');

@keyframes colorFade {
  0% { color: #ffab00; }  /* Amber Accent-4 */
  50% { color: #ffc247; } /* Laranja escuro */
  100% { color: #ffdb92; } /* Volta ao original */
}

.oleo-script-bold {
  font-family: "Oleo Script", system-ui;
  font-weight: 700;
  font-style: normal;
}

.color-logo{
    animation: colorFade 2s infinite alternate;
}
</style>