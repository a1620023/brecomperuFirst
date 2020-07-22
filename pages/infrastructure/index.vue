<template>
  <div>

<!-- Titulo de la pagina -->
    <div>
      <v-row class="light-blue accent-3" justify="center">
        <v-alert
          class="light-blue accent-3"
          dark
          icon="mdi-server-security"
          prominent
        >
          <h2 class="text-captation">Infraestructura Tecnológica</h2>
        </v-alert>
      </v-row>
    </div>

<!-- Descripcion de la pagina -->
    <div>
      <v-hover v-slot:default="{ hover }" open-delay="200">
        <v-banner two-line :elevation="hover ? 16 : 2">
          <v-row justify="center">
            <v-col cols="12" sm="6">
              Enfocado a Proveer e Implementar Infraestructuras de TI respaldado
              por las principales marcas internacionales.
            </v-col>
          </v-row>
        </v-banner>
      </v-hover>
    </div>

    <div>
      <v-timeline align-top :dense="$vuetify.breakpoint.smAndDown">
        <v-timeline-item v-for="(item, i) in items" :key="i.id" fill-dot>
          <template v-slot:icon>
            <v-icon large color="purple darken-2">{{ item.src }}</v-icon>
          </template>
          <template v-slot:opposite>
            <v-card>
              <v-img :src="item.img" />
            </v-card>
          </template>
          <v-card :color="item.color" dark>
            <v-card-title class="title">
              <h2>{{ item.title }}</h2>
            </v-card-title>
            <v-container class="white text--primary">
              <v-row>
                <v-col cols="12" md="10">
                  {{ item.description }}
                </v-col>
              </v-row>
              <v-row>
                <v-col>
                  <v-btn :color="item.color" dark class="mx-0" outlined>
                    Más
                  </v-btn>
                </v-col>
              </v-row>
            </v-container>
          </v-card>
        </v-timeline-item>
      </v-timeline>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        title: 'Servidores',
        color: 'light-green darken-1',
        src: 'mdi-server',
        img: 'https://i.ibb.co/6bvzG0k/DATABASE.png',
        description:
          'Atendemos sus requerimientos con los servidores de las marcas más reconocidad del mercado, con la garantia y respaldo directo del fabricante.',
      },
      {
        title: 'WorkStations',
        color: 'blue lighten-1',
        src: 'mdi-desktop-tower-monitor',
        img: 'https://i.ibb.co/6bvzG0k/DATABASE.png',
        description:
          'Más eficientes para trabajos que demandan alto uso de recursos de computo.',
      },
      {
        title: 'Laptops',
        color: 'cyan lighten-1',
        src: 'mdi-laptop-windows',
        img: 'https://i.ibb.co/6bvzG0k/DATABASE.png',
        description:
          'Eficientes y de alta calidad para trabajos que requieren constante movimiento.',
      },
      {
        title: 'Monitores',
        color: 'teal accent-3',
        src: 'mdi-monitor-screenshot',
        img: 'https://i.ibb.co/6bvzG0k/DATABASE.png',
        description:
          'Pantallas de gama alta para Calidad de imagen y características profesionales.',
      },
    ],
  }),
  head() {
    return {
      title: 'Infraestructura',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Infraestructura Tecnológica',
        },
      ],
      htmlAttrs: {
        lang: 'es',
      },
    }
  },
}
</script>
<style scoped>
.alinear-subtitulo {
  margin-inline-end: auto;
}
</style>
