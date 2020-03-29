<template>
  <div class="VueToNuxtLogo">
    <v-card>
      <v-card-title class="headline">
        News
      </v-card-title>
      <v-card-text>
        <p>幼少期から活発でした。</p>
        <hr class="my-3">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
        >
          Nuxt Documentation
        </a>
        <br>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
        >
          Nuxt GitHub
        </a>
      </v-card-text>
      <v-card-actions>
        <v-spacer />
        <v-btn
          color="primary"
          nuxt
          to="/inspire"
        >
          Continue
        </v-btn>
      </v-card-actions>
    </v-card>
    <div class="Triangle Triangle--two" />
    <div class="Triangle Triangle--one" />
    <div class="Triangle Triangle--three" />
    <div class="Triangle Triangle--four" />
  </div>
</template>

<style>
</style>
