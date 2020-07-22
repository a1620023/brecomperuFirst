<template>
  

      <v-carousel v-model="window" show-arrows-on-hover cycle height="auto">
        <v-carousel-item v-for="(item, i) in CarouselImg" :key="i.id">
          <v-img :aspect-ratio="17 / 9" :src="item.src" :alt="item.alt" />
        </v-carousel-item>
      </v-carousel>


</template>

<script>
export default {
  data() {
    return {
      window: 0,
      CarouselImg: [
        {
          src: 'https://i.ibb.co/f83JyvC/SSL-CERTIFICATE.png',
          alt: 'Certificado SSL',
        },
        {
          src: 'https://i.ibb.co/KmNJVDF/HOSTING.png',
        },
        {
          src: 'https://i.ibb.co/6bvzG0k/DATABASE.png',
        },
      ],
    }
  },
}
</script>
