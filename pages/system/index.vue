<template>
  <div>

<!-- Titulo de la pagina -->
    <div>
      <v-row class="light-blue accent-3" justify="center">
        <v-alert
          class="light-blue accent-3"
          dark
          icon="mdi-server-security"
          prominent>
          <h2 class="text-captation">DESARROLLO DE SISTEMAS</h2>
        </v-alert>
      </v-row>
    </div>

<!-- Descripcion de la pagina -->
    <div>
      <v-hover v-slot:default="{ hover }" open-delay="100">
        <v-banner two-line :elevation="hover ? 16 : 2">
          <v-row justify="center">
            <v-col cols="12" sm="6">
              Optimiza tareas rutinarias, automatiza procesos
            </v-col>
          </v-row>
        </v-banner>
      </v-hover>
    </div>

<!-- Imagen promoconal de la pagina -->
    <div>
      <v-img
        :aspect-ratio="16 / 9"
        height="auto"
        src="https://i.ibb.co/yhdnrDP/bp-sistemas.png">
        <v-row justify="center" align="end" class="lightbox white--text pa-2 fill-height">
          <v-col class="text-size" cols="12" sm="9">
            Solicita ahora mismo una cotización
          </v-col>
          <v-spacer/>
          <v-col cols="6" sm="3">
            <v-btn dark class="mx-0" outlined>
              <p class="btn-size">Solicitar Cotización</p>
            </v-btn>
          </v-col>
        </v-row>
      </v-img>
    </div>

    <v-container>
      <v-card :elevation="18" class="mx-auto light-blue lighten-1">
        <v-card-title class="display-1 white--text text-captation">
          Desarrollo de sistemas a medida
        </v-card-title>
      </v-card>
    </v-container>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Sistemas',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Desarrollo de sistemas a medida',
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
.text-size {
  font-size:2vw;
}
.btn-size {
  font-size:2vw;
}
</style>