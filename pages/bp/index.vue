<template>
  <div>
    <div>
      <v-layout column justify-center align-center>
        <v-flex>
          <BrecomperuLogo />
        </v-flex>
      </v-layout>
    </div>

    <div>
      <v-card :elevation="18" class="phrase mx-auto primary" max-width="900">
        <p class="text-captation white--text">
          Soluciones que crean oportunidades
        </p>
      </v-card>
    </div>

    <div>
      <v-row>
        <v-col v-for="(item, i) in AboutCompany" :key="i.id">
          <v-hover>
            <template v-slot:default="{ hover }">
              <v-card class="mx-auto" max-width="344">
                <v-img :src="item.img" :alt="item.title"></v-img>

                <v-card-text>
                  <h2 class="title primary--text">{{ item.title }}</h2>
                  {{ item.description }}
                </v-card-text>

                <v-card-title>
                  <v-rating
                    :value="4"
                    dense
                    color="orange"
                    background-color="orange"
                    hover
                    class="mr-2"
                  ></v-rating>
                  <span class="primary--text subtitle-2">64 Visitas</span>
                </v-card-title>

                <v-fade-transition>
                  <v-overlay v-if="hover" absolute color="#036358">
                    <v-btn>Más Información Pronto</v-btn>
                  </v-overlay>
                </v-fade-transition>
              </v-card>
            </template>
          </v-hover>
        </v-col>
      </v-row>
    </div>

  </div>
</template>

<script>
import BrecomperuLogo from '~/components/BrecomperuLogo.vue'
// import Data from '@/data/aboutCompany.json'

export default {
  components: {
    BrecomperuLogo,
  },
  data: () => ({
    collapseOnScroll: true,
    overlay: false,
    AboutCompany: [
      {
        id: 1,
        title: 'QUIENES SOMOS',
        description:
          'Somos una empresa de Investigación de Soluciones Tecnológicas, Consultoría TI, Desarrollo de Software e Infraestructuras TI.',
        content: [
          {
            id: 1,
            information:
              'En Brecomperu, consideramos que la prestación de servicios y producción de soluciones de la más alta calidad es una palanca imprescindible para la sostenibilidad de la organización y la creación de valor para todas las partes interesadas.',
          },
          {
            id: 2,
            information: '',
          },
        ],
        img: 'https://cdn.vuetifyjs.com/images/cards/forest-art.jpg',
        href: '',
      },
      {
        id: 2,
        title: 'QUE HACEMOS',
        description:
          'En Brecomperu creamos soluciones y servicios innovadores contribuyendo al desarrollo, no sólo en beneficio de nuestros clientes sino, en un sentido más amplio, a toda la sociedad y en las comunidades donde estamos presentes.',
        content: [
          {
            id: 1,
            information:
              'Creamos y diseñamos soluciones acordes a sus objetivos aportando en el desarrollo, la transformación e innovación de sus negocios.',
          },
          {
            id: 2,
            information: 'Desarrollo de Software',
          },
          {
            id: 3,
            information: 'Infraestructura Tecnológica',
          },
          {
            id: 4,
            information: 'Servicios de Consultoría en TI',
          },
          {
            id: 4,
            information: 'Investigación y Pruebas de Concepto',
          },
        ],
        img: 'https://cdn.vuetifyjs.com/images/cards/forest-art.jpg',
        href: '',
      },
      {
        id: 3,
        title: 'DONDE ESTAMOS',
        description:
          'Estamos presentes en toda la región latam con nuestro servico bp_web y bp_cloud atravez de nuestros socos estrategicos, teniendo como ubicación física nuestra sede principal en lima, Perú.',
        content: [
          {
            id: 1,
            information: '',
          },
        ],
        img: 'https://cdn.vuetifyjs.com/images/cards/forest-art.jpg',
        href: '',
      },
      {
        id: 4,
        title: 'CON QUIENES TRABAJAMOS',
        description:
          'Nuestras soluciones están orientadas principalmente a las empresas con visión de cambio y constante innovación.',
        content: [
          {
            id: 1,
            information: '',
          },
        ],
        img: 'https://cdn.vuetifyjs.com/images/cards/forest-art.jpg',
        href: '',
      },
    ],
  }),
  head() {
    return {
      title: 'About',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Pruebas de concepto a bajo costo',
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
.phrase {
  text-align: center;
  font-size: 2em;
}
</style>
