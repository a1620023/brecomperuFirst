<template>
<div>
  <!-- Titulo de la pagina -->
    <div>
      <v-row class="light-blue accent-3" justify="center">
        <v-alert
          class="light-blue accent-3" dark
          icon="mdi-server-security"
          prominent>
          <h2 class="text-captation">Laboratorio de tecnología a bajo costo</h2>
        </v-alert>
      </v-row>
    </div>

<!-- Descripcion de la pagina -->
    <div>
      <v-hover v-slot:default="{ hover }" open-delay="200">
        <v-banner two-line :elevation="hover ? 16 : 2">
          <v-row justify="center">
            <v-col cols="12" sm="6">
              Pruebas de concepto para proyectos de tecnología.
            </v-col>
          </v-row>
        </v-banner>
      </v-hover>
    </div>

  <v-layout>
      <v-flex>
          <v-row>
              <v-col>
                  <v-card>
                      <v-card-title>Producto Mínimo Viable</v-card-title>
                      <v-card-text>Probamos rápidamente de manera cuantitativa y cualitativa la respuesta del mercado a un producto o una funcionalidad específica.</v-card-text>
                      <v-card-subtitle>En BP_LAB lo desarrollamos, tú lo vendes</v-card-subtitle>
                  </v-card>
              </v-col>
              <v-col>
                  <v-card>
                      <v-card-title>Pruebas de Concepto</v-card-title>
                      <v-card-text>Verificamos que los conceptos y teorías aplicados a un proyecto tendrán una aplicación en el mundo real.</v-card-text>
                      <v-card-subtitle>Documentamos su viabilidad técnica</v-card-subtitle>
                  </v-card>
              </v-col>
              <v-col>
                  <v-card>
                      <v-card-title>Prototipo</v-card-title>
                      <v-card-text>En BP_LAB Desarrollamos el Modelo.</v-card-text>
                      <v-card-subtitle>Tu lo Verificas</v-card-subtitle>
                      <v-btn
                        v-if="!chip1 && !chip2 && !chip3"
                        close
                        color="primary"
                        dark
                        @click="chip1 = true, chip2 = true, chip3 = true">
                          Prototipo Confirmado
                      </v-btn>
                        <v-chip
                        v-if="chip1"
                        class="ma-2"
                        close
                        color="green"
                        text-color="green"
                        label
                        outlined
                        @click:close="chip1 = false">
                          Aprender
                      </v-chip>
                      <v-chip
                        v-if="!chip1 && chip2"
                        class="ma-2"
                        close
                        color="orange"
                        text-color="orange"
                        label
                        outlined
                        @click:close="chip2 = false">
                          Probar
                      </v-chip>
                      <v-chip
                        v-if="!chip1 && !chip2 && chip3"
                        class="ma-2"
                        close
                        color="red"
                        text-color="red"
                        label
                        outlined
                        @click:close="chip3 = false">
                          Testear
                      </v-chip>
                  </v-card>
              </v-col>
          </v-row>
          <v-row>
              <v-col
                v-for="(item, i) in items"
                :key="i"
                cols="12">
                  <v-card
                    :color="item.color"
                    dark>
                        <v-row>
                            <v-col>
                                <v-card-title
                                    class="headline"
                                    v-text="item.title"></v-card-title>
                                <v-card-subtitle v-text="item.artist"></v-card-subtitle>
                            </v-col>
                            <v-col>
                                <v-avatar
                                    size="360"
                                    tile>
                                    <v-img  :aspect-ratio="16 / 9" :src="item.src"></v-img>
                                </v-avatar>
                            </v-col>
                        </v-row>
                  </v-card>
              </v-col>
          </v-row>
      </v-flex>
  </v-layout>
</div>
</template>

<script>
export default {
    data () {
      return {
        chip1: true,
        chip2: true,
        chip3: true,
        items: [
        {
          color: '#1F7087',
          src: '/lab/playMVP.svg',
          alt: 'Producto Minimo Viable MVP',
          title: 'Desarrollamos tu MVP',
          artist: 'Si estas planeando probar o implementar una nueva tecnologia BP_LAB tiene el aquipo investigadores que necesitas',
        },
        {
          color: '#952175',
          src: '/lab/presentMVP.svg',
          alt: 'Presentacion de MVP',
          title: 'Prueba y testea tu Modelo',
          artist: 'Te entregamos tu modelo desarrollado y listo para que ejecutes las prubas en un escenario real.',
        },
      ],
      }
    },
}
</script>
