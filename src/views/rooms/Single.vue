<template>
  <v-row justify="center">
    <v-col md="10" xl="7" class="px-sm-10 mt-sm-3">
      <PhotoGallery :images="images" />
      <v-row class="px-8 px-sm-0 mt-1 mb-5" justify="center">
        <v-col cols="12" md="8">
          <p class="text-h5 font-weight-medium">Solteiro</p >
          <p class="text-subtitle-1">1 hóspede • 1 cama</p>

          <v-divider class="my-4"/>
          <p class="text-h6 font-weight-medium">Comodidades</p >
          <v-row>
            <v-col>
              <v-list bg-color="background">
                <RoomFeature icon="mdi-bed-outline" text="Cama de solteiro" />
                <RoomFeature icon="mdi-shower-head" text="Banheiro privado" />
                <RoomFeature icon="mdi-coffee-outline" text="Café da manhã" />
              </v-list>
            </v-col>
            <v-col>
              <v-list bg-color="background">
                <RoomFeature icon="mdi-wifi" text="Rede Wi-Fi" />
                <RoomFeature icon="mdi-television" text="Televisão LED" />
                <RoomFeature icon="mdi-snowflake" text="Ar condicionado" />
              </v-list>
            </v-col>
          </v-row>
        </v-col>
        <v-col class="text-center">
          <!-- <v-btn
            v-if="xs"
            color="primary"
            variant="flat"
            size="large"
            prepend-icon="mdi-calendar-clock"
            text="Reservar"
          /> -->
          <v-card border class="h-">
            <v-card-text class="my-5">
              <p class="text-body-1 font-weight-bold">Reserve antes que esgote!</p>
              <p class="text-subtitle-2 font-weight-light">A reserva online é fácil, rápida e segura.</p>
              <v-btn
                color="primary"
                variant="flat"
                block
                size="x-large"
                prepend-icon="mdi-calendar-clock"
                text="Reservar"
                class="mt-4"
                :href="bookingUrl({ room: RoomType.Single, })"
                target="_blank"
              />
              <v-divider class="my-7"/>
              <v-btn variant="outlined" icon="mdi-whatsapp" class="mr-5"/>
              <v-btn variant="outlined" icon="mdi-phone-outline" />
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-col>
  </v-row>
</template>

<script setup lang="ts">
import { useHead } from '@vueuse/head'
useHead({
  title: 'Pé da Serra Hotel',
  meta: [
    {
      name: 'description',
      content: 'Quarto de solteiro.',
    },
  ],
});

import PhotoGallery from '@/components/PhotoGallery.vue';
import RoomFeature from '@/components/RoomFeature.vue';
import img1 from "@/assets/single-1.jpg";
import img2 from "@/assets/single-2.jpg";
import img3 from "@/assets/single-3.jpg";
import img4 from "@/assets/single-4.jpg";
import img5 from "@/assets/single-5.jpg";

const images = [img1, img2, img3, img4, img5];

import { bookingUrl, RoomType } from '@/features/booking';
</script>
