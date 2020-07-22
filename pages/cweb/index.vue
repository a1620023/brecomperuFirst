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
          <h2 class="text-captation">Servicios para sistemas web</h2>
        </v-alert>
      </v-row>
    </div>

<!-- Descripcion de la pagina -->
    <div>
      <v-hover v-slot:default="{ hover }" open-delay="200">
        <v-banner two-line :elevation="hover ? 16 : 2">
          <v-row justify="center">
            <v-col cols="12" sm="6">
              Correos corporativos, Bases de Datos remotos, Servicios de Hosting y Certificados SSL para Soluciones Web.
            </v-col>
          </v-row>
        </v-banner>
      </v-hover>
    </div>

    <v-container>
      <v-row justify="center">
        <v-expansion-panels popout focusable>
          <v-expansion-panel v-for="(item, i) in ServiciosWeb" :key="i.id">
            <v-expansion-panel-header>
              {{ item.title }}
              <template v-slot:actions>
                <v-icon color="teal">{{ item.icon}}</v-icon>
              </template>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              <v-row>
                <v-col>
                  {{ item.description }}
                </v-col>
                <v-col>
                  <v-btn>Ver Más</v-btn>
                </v-col>
              </v-row>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-row>
    </v-container>

    <v-container>
      <v-row align="center">
        <v-carousel v-model="window" :show-arrows="false" :vertical="vertical" :cycle="true">
          <v-carousel-item
            v-for="(item, i) in ServiciosWeb"
            :key="i.id"
            :src="item.img"
          ></v-carousel-item>
        </v-carousel>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    length: 3,
    window: 0,
    vertical: true,
    autorun: true,
    ServiciosWeb: [
      {
        id: 1,
        title: "Correos Corporativos",
        icon: 'mdi-email',
        description:"Envía información de forma segura y libre de publicidad con los correos corporativos",
        img: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        alt:'Correos Corporativos',
        to: '',
      },
      {
        id: 2,
        title: "Dominios",
        icon: 'mdi-domain',
        description:'Un Dominio es una parte escencial y necesario para establecer tu negocio en Internet, es un identificador de tu negocio que se utiliza en la dirección de tu pagina o sitio en Internt. En Brecomperu te ayudamos con la busqueda, adquicición y la configuración, ya sea integrando con nuestro Hosting o de terceros.',
        img: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        alt:'Correos Corporativos',
        to: '',
      },
      {
        id: 3,
        title: "Base de Datos Remoto",
        icon: 'mdi-server',
        description:"Con el Acceso Directo a Base de Datos le permite administrar en remoto las bases de datos en su cuenta de alojamiento con herramientas externas tales como Microsoft SQL Server Management Studio Express y MySQL Query Browser",
        img: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        alt:'Correos Corporativos',
        to: '',
      },
      {
        id: 4,
        title: "Hosting",
        icon: 'mdi-desktop',
        description:"Envía incidad con los correos corporativos",
        img: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        alt:'Correos Corporativos',
        to: '',
      },
      {
        id: 5,
        title: "Certificados SSL",
        icon: 'mdi-security',
        description:"Envidad con los correos corporativos",
        img: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
        alt:'Correos Corporativos',
        to: '',
      },
    ],
  }),

  created() {
    setInterval(() => {
      if (!this.autorun) return
      if (++this.window >= this.length) this.window = 0
    }, 5000)
  },
}
</script>
