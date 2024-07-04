<template>
  <div>
    <VApp>
      <VMain>
        <v-app-bar class="top-bar" density="compact" color="#7986CB">
          <template v-slot:prepend>
            <img src="/gak-logo.png" alt="" class="gak-logo" />
          </template>

          <v-app-bar-title>UEFA EURO 2024</v-app-bar-title>

          <template v-slot:append>
            <v-btn icon="mdi-help-circle-outline" size="large"></v-btn>
          </template>
        </v-app-bar>

        <slot />
      </VMain>
    </VApp>
  </div>
</template>

<style>
.gak-logo {
  max-height: 100%;
  height: calc(100% - 18px);
  margin-left: 6px;
}
</style>
