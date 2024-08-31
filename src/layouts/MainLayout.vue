<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-avatar size="80px">
          <img src="assets/images/KCMLogo.png" @click="scrollToTop()" />
        </q-avatar>
        <q-toolbar-title> KC Riichi </q-toolbar-title>
        <router-link to="/routename"></router-link>

        <div class="socials">
          <div><p>Socials:</p></div>
          <q-btn
            class="button-size"
            href="https://quasar.dev/options/installing-icon-libraries"
            flat
            icon="fa-brands fa-instagram"
            size="1.3em"
          />
          <q-btn
            class="button-size"
            href="https://quasar.dev/options/installing-icon-libraries"
            flat
            icon="fa-brands fa-discord"
            size="1.3em"
          />
        </div>
      </q-toolbar>
    </q-header>
    <q-page-container class="page-style">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
defineOptions({
  name: 'MainLayout',
});

function scrollToTop() {
  window.scroll({
    top: 0,
    left: 0,
    behavior: 'smooth',
  });
}
</script>

<style>
.socials {
  display: flex;
  flex-flow: row;
  align-items: center;
}

p {
  vertical-align: middle;
  margin: 0px;
  font-size: medium;
}

.button-size {
  padding: 4px 8px;
}

/* Page Header */
h1 {
  font-family: 'poppins', sans-serif;
  font-weight: 600;
  line-height: 1.5;
  font-size: 36px;
  text-align: center;
}

/* Overall Section */
h2 {
  font-family: 'poppins', sans-serif;
  font-weight: 600;
  line-height: 1.5;

  font-size: 30px;
  margin: 20px 0 18px 0;

  text-align: center;
}

/* Sub Section */
h3 {
  font-family: 'poppins', sans-serif;
  font-weight: 600;
  line-height: 1.5;

  font-size: 24px;
  margin: 0 0 0 0;
}

p {
  font-family: 'Poppins', sans-serif;
  font-size: 22px;
  font-weight: 500;
  line-height: 1.6em;
}

.text-center {
  text-align: center;
}

b {
  font-weight: 700;
}

.page-style {
  background-color: var(--q-secondary);
}
</style>
../constants/sideNavItems
