<template>
  <v-card max-width="1400" class="mx-auto">
    <v-system-bar color="pink darken-2" dark>
    </v-system-bar>

    <v-app-bar dark color="pink">
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>My Audiothek</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
    </v-app-bar>

    <!-- Card Carousel Section -->
    <v-sheet class="overflow-hidden" height="220">
      <v-slide-group
        v-model="selectedSlide"
        class="pa-4"
        show-arrows
        mandatory
      >
        <v-slide-item
          v-for="(item, i) in items"
          :key="i"
        >
          <v-card
            :color="item.color"
            dark
            class="ma-2"
            width="300"
            @click="selectSlide(i)"
          >
            <div class="d-flex flex-no-wrap justify-space-between">
              <div>
                <v-card-title class="text-h5" v-text="item.title"></v-card-title>
                <v-card-subtitle v-text="item.artist"></v-card-subtitle>
                <v-card-actions>
                  <v-btn
                    class="ml-2 mt-3"
                    fab
                    icon
                    height="40px"
                    right
                    width="40px"
                  >
                    <v-icon>mdi-download</v-icon>
                  </v-btn>
                </v-card-actions>
              </div>
              <v-avatar class="ma-3" size="125" tile>
                <v-img :src="item.src"></v-img>
              </v-avatar>
            </div>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    selectedSlide: 0,
    items: [
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
        title: 'Supermodel',
        artist: 'Foster the People',
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
        title: 'Halcyon Days',
        artist: 'Ellie Goulding',
      },
      {
        color: '#1F7087',
        src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
        title: 'Another Album',
        artist: 'Another Artist',
      },
      {
        color: '#952175',
        src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
        title: 'Fourth Album',
        artist: 'Fourth Artist',
      },
    ],
  }),
  methods: {
    selectSlide(index) {
      this.selectedSlide = index;
    }
  },
}
</script>