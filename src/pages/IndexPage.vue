<template>
  <main class="">
    <div class="horizontal-flex">
      <q-img :src="logo" class="logo-size" />
      <h1>Kansas City Riichi Mahjong</h1>
    </div>
    <div class="vertical-divider"></div>
    <p>
      Our goal is to grow and foster the community for
      <span class="highlight">Riichi Mahjong</span> and invite all to join us to
      learn and play. We hold meet-ups for casual and intermediate and have a
      growing discord community with other Midwest locals. Whether you are a
      total beginner or an experienced player who loves to nerd out about
      Mahjong, you've come to the right place.
    </p>
    <div class="vertical-divider"></div>
    <q-carousel animated v-model="slide" arrows navigation infinite>
      <q-carousel-slide :name="1" img-src="assets/images/hello.jpg" />
      <q-carousel-slide :name="2" img-src="assets/images/group.jpg" />
      <q-carousel-slide :name="3" img-src="assets/images/lpm-event1.jpg" />
      <q-carousel-slide :name="4" img-src="assets/images/lpm-event3.jpg" />
      <q-carousel-slide :name="5" img-src="assets/images/lpm-event2.jpg" />
      <q-carousel-slide :name="6" img-src="assets/images/con-event.jpg" />
      <q-carousel-slide :name="7" img-src="assets/images/sticks.jpg" />
    </q-carousel>

    <h2>
      Check out our instagram, discord community, calendar of events, and visit
      us at one of our meet-ups!
    </h2>
    <div class="horizontal-flex">
      <q-btn
        flat
        color="blue"
        href="https://www.instagram.com/kc_riichi?igsh=bXI4NzMwbnZvNzJq&utm_source=qr"
      >
        <q-icon size="3em" name="fa-brands fa-instagram" color="black" />
      </q-btn>
      <q-btn flat color="blue" href="https://discord.gg/M8kxEfn">
        <q-icon size="3em" name="fa-brands fa-discord" color="black" />
      </q-btn>
      <q-btn flat color="blue" href="mailto: kcriichi@gmail.com">
        <q-icon size="3em" name="fa fa-envelope" color="black" />
      </q-btn>
    </div>
    <h2>Upcoming Events</h2>
    <div class="vertical-divider"></div>
    <div class="horizontal-flex">
      <iframe
        src="https://calendar.google.com/calendar/embed?height=800&wkst=1&ctz=America%2FChicago&bgcolor=%23F6BF26&showCalendars=0&src=a2NyaWljaGlAZ21haWwuY29t&color=%23D50000&mode=agenda&showTitle=0&showPrint=0&showDate=0&showNav=0&showTabs=0"
        style="border: solid 1px #777"
        frameborder="0"
        scrolling="no"
        height="700px"
        width="60%"
      ></iframe>
      <div class="vertical-divider"></div>
    </div>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const logo = ref('assets/images/KCMLogo.png');
const slide = ref(1);
</script>

<style>
main {
  margin: 0 auto;
  padding: 30px;
  max-width: 1024px;
  min-height: 300px;
}

.horizontal-flex {
  display: flex;
  justify-content: center; /*keep*/
  align-items: center; /*Keep*/
}

.vertical-divider {
  min-height: 1.5rem;
}

.highlight {
  color: var(--q-primary);
  font-weight: bold;
}

.logo-size {
  height: 160px;
  max-width: 160px;
  margin-right: 10px;
}
</style>
