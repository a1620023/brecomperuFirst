<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>

<!-- Este es el menu oculto que aparece cuando es responsive -->
      <v-navigation-drawer
        v-model="drawer"
        :mini-variant="miniVariant"
        :clipped="clipped"
        app>
        <v-list>
          <v-list-item
            v-for="(item, i) in areasNegocio"
            :key="i.id"
            :to="item.to"
            router
            exact>
            <v-list-item-action>
              <v-icon color="blue darken-2">{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title v-text="item.title" />
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <v-app-bar
        color="deep-purple accent-4"
        dark
        prominent
        :clipped-left="clipped"
        shrink-on-scroll
        src="https://i.ibb.co/n3y7NVs/bp-fondo-azul.png"
        app>

<!-- Esto es el logo como icono -->
        <v-row align="center" justify="center">
          <v-col cols="12" align="center">
            <v-app-bar-nav-icon class="posicion-logo-icon">
              <BrecomperuIcon />
              <!-- <v-img
                class="logo-size"
                src="https://i.ibb.co/Xx1KGrn/BP-company-alas-esfera-icon.png"
              /> -->
            </v-app-bar-nav-icon>
          </v-col>
        </v-row>

<!-- Aqui estan los bottones de navegacion y el titulo de la pagina -->
        <v-row align="center" justify="center">
          <v-col cols="12" align="center">
            <v-toolbar-title to="/" tag="span" style="cursor: pointer">
              <v-img
                class="name-size"
                src="https://i.ibb.co/p2kHdYw/BP-company-nombre-b-icon.png"
              />
            </v-toolbar-title>
          </v-col>
          <v-col cols="12" align="center">
            <v-app-bar-items class="hidden-xs-only">
              <v-btn
                class="ma-2"
                rounded
                color="primary"
                v-for="(item, i) in areasNegocio"
                :key="i.id"
                :to="item.to"
                router
                exact
              >
                {{ item.title }}
              </v-btn>
            </v-app-bar-items>
          </v-col>
        </v-row>

<!-- Este es el responsive botton oculto -->
        <v-row align="center" justify="center">
            <v-col cols="12" align="center">
                <span class="hidden-sm-and-up">
                    <v-app-bar-nav-icon @click.stop="drawer = !drawer">
                    </v-app-bar-nav-icon>
                </span>
            </v-col>
        </v-row>

<!-- Este es el botton flotante de las redes sociales -->
        <v-row align="center" justify="center">
            <v-col cols="12" align="center">
                <v-speed-dial
                v-model="fab"
                :top="top"
                :bottom="bottom"
                :right="right"
                :direction="direction"
                :open-on-hover="hover"
                :transition="transition">
                <template v-slot:activator>
                    <v-btn v-model="fab" small color="pink darken-2" dark fab class="posicion-icon">
                    <v-icon v-if="fab">mdi-close</v-icon>
                    <v-icon v-else>mdi-account-circle</v-icon>
                    </v-btn>
                </template>
                <v-btn
                    fab
                    dark
                    small
                    color="green"
                    v-for="icon in redes"
                    :key="icon.id"
                    class="mx-3"
                    icon>
                    <a
                    class="text-decoration-none"
                    :href="icon.url"
                    :target="icon.target">
                    <v-btn
                        class="mx-2 font-weight-medium text-lowercase"
                        fab
                        dark
                        small
                        color="primary">
                        <v-icon>{{ icon.icon }}</v-icon>
                    </v-btn>
                    </a>
                </v-btn>
                </v-speed-dial>
            </v-col>
        </v-row>

      </v-app-bar>
    </v-flex>
  </v-layout>
</template>

<script>
import BrecomperuIcon from '~/components/BrecomperuIcon.vue'

export default {
      components: {
    BrecomperuIcon
  },
  data() {
    return {
      drawer: false,
      miniVariant: false,
      direction: 'bottom',
      fab: false,
      hover: true,
      transition: "slide-y",
      clipped: true,
      right: true,
      areasNegocio: [
        {
          icon: "mdi-home",
          title: "inicio",
          to: "/"
        },
        {
          icon: "mdi-head-sync-outline",
          title: "bp lab",
          to: "/lab"
        },
        {
          icon: "mdi-desktop-mac-dashboard",
          title: "sistemas",
          to: "/system"
        },
        {
          icon: "mdi-server-network",
          title: "infraestructuras",
          to: "/infrastructure"
        },
        {
          icon: "mdi-cloud-tags",
          title: "cloud",
          to: "/cloud"
        },
        {
          icon: "mdi-navigation",
          title: "adds",
          to: "/adds"
        },
        {
          icon: "mdi-web",
          title: "web",
          to: "/cweb"
        },
        {
          icon: "mdi-domain",
          title: "brecomperu",
          to: "/bp"
        }
      ],
      redes: [
        {
          icon: "mdi-instagram",
          title: "in",
          url: "https://www.instagram.com/brecomperu/?hl=es-la",
          target: "_blank"
        },
        {
          icon: "mdi-facebook",
          title: "fa",
          url: "https://www.facebook.com/Brecomperu-111266247130977/",
          target: "_blank"
        }
      ]
    };
  },
};
</script>

<style>

.posicion-logo-icon {
  margin-top: -40px;
}
.posicion-icon {
    margin-top: -10px;
}
.logo-size {
  width: 70px;
}
.name-size {
  width: 200px;
}
</style>
