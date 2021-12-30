<template>
  <v-container class="pt-7 pl-5 pb-16">
    <v-row no-gutters class="d-flex justify-space-between">
      <div>
        <div class="subtitle-2">
          Location <v-icon x-small>mdi-chevron-down </v-icon>
        </div>
        <div class="font-weight-bold">
          <v-icon color="pink darken-2">mdi-map-marker </v-icon>Indonesia
        </div>
      </div>
      <div>
        <v-card elevation="2">
          <v-icon large>mdi-bell-badge-outline</v-icon>
        </v-card>
      </div>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-text-field
          solo
          hide-details
          label="Search Property"
          prepend-inner-icon="mdi-magnify"
          class="rounded-lg"
        ></v-text-field>
      </v-col>
    </v-row>
    <!-- Popular -->
    <v-row>
      <v-container>
        <v-col>
          <v-row> <h2>Popular</h2> </v-row>
          <v-row class="fill-width">
            <v-col
              cols="10"
              sm="6"
              md="6"
              lg="3"
              v-for="popular in popularList"
              :key="popular.id"
            >
              <v-card
                :loading="loading"
                class="mx-auto my-2 rounded-lg"
                max-width="374"
              >
                <v-container>
                  <v-img
                    height="250"
                    :src="require(`@/assets/` + popular.imgUrl)"
                    class="rounded-lg"
                  ></v-img>
                </v-container>
                <v-card-title class="justify-space-between">
                  <h3>{{ popular.name }}</h3>
                  <v-icon> mdi-heart-outline </v-icon>
                </v-card-title>

                <v-card-text>
                  <div class="text-subtitle-1">
                    <v-icon>mdi-map-marker</v-icon> {{ popular.location }}
                  </div>
                  <v-list-item class="grow pr-0">
                    <v-row align="center">
                      <v-icon class="mr-1"> mdi-bed-king-outline </v-icon>
                      <span class="subheading mr-2">4</span>
                      <span class="mr-1">·</span>
                      <v-icon class="mr-1" small> mdi-shower </v-icon>
                      <span class="subheading">3</span>
                    </v-row>
                    <v-list-item-action>
                      <v-list-item-title
                        ><Strong class="pink--text text--darjken-3">
                          ${{ popular.annualPrice }}/Year
                        </Strong></v-list-item-title
                      >
                    </v-list-item-action>
                  </v-list-item>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
      </v-container>
    </v-row>
    <!-- Recommended -->
    <v-row>
      <v-container>
        <v-col>
          <v-row> <h2>Recommended for you</h2> </v-row>
          <v-row class="fill-width">
            <v-col
              cols="12"
              sm="8"
              md="8"
              lg="4"
              v-for="popular in popularList"
              :key="popular.id"
            >
              <v-card :loading="loading" class="mx-auto my-2 rounded-lg">
                <div class="d-flex">
                  <v-img
                    height="140"
                    width="30"
                    :src="require(`@/assets/` + popular.imgUrl)"
                    class="rounded-lg ml-2 mt-2"
                  ></v-img>
                  <div class="d-flex flex-column">
                    <v-card-title class="justify-space-between">
                      <h5>{{ popular.name }}</h5>
                      <v-icon> mdi-heart-outline </v-icon>
                    </v-card-title>

                    <v-card-text>
                      <div class="text-subtitle-1">
                        <v-icon>mdi-map-marker</v-icon> {{ popular.location }}
                      </div>
                      <v-list-item class="grow pr-0">
                        <v-row align="center">
                          <v-icon class="mr-1"> mdi-bed-king-outline </v-icon>
                          <span class="subheading mr-2">4</span>
                          <span class="mr-1">·</span>
                          <v-icon class="mr-1" small> mdi-shower </v-icon>
                          <span class="subheading">3</span>
                        </v-row>
                        <v-list-item-action>
                          <v-list-item-title
                            ><Strong class="pink--text text--darjken-3">
                              ${{ popular.annualPrice }}/Year
                            </Strong></v-list-item-title
                          >
                        </v-list-item-action>
                      </v-list-item>
                    </v-card-text>
                  </div>
                </div>
              </v-card>
            </v-col>
          </v-row>
        </v-col>
      </v-container>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Home",

  data: () => ({
    loading: false,
    selection: 1,
    popularList: [
      {
        id: 1,
        name: "Zila Homes",
        imgUrl: "home-pool.jpg",
        location: "Bandung, Indonesia",
        annualPrice: "80.00",
      },
      {
        id: 2,
        name: "Honey Homes",
        imgUrl: "home-pool-2.jpg",
        location: "Bogor, Indonesia",
        annualPrice: "80.00",
      },
      {
        id: 3,
        name: "Adila Homes",
        imgUrl: "home-pool-3.jpg",
        location: "Kalimantan, Indonesia",
        annualPrice: "80.00",
      },
    ],
  }),

  methods: {},
};
</script>

<style scoped>
.fill-width {
  overflow-x: auto;
  flex-wrap: nowrap;
}

.v-sheet.v-card:not(.v-sheet--outlined) {
  box-shadow: rgb(0 0 0 / 10%) 0px 10px 15px -3px,
    rgb(0 0 0 / 5%) 0px 4px 6px -2px;
}

.v-input__slot {
  box-shadow: rgb(0 0 0 / 10%) 0px 10px 15px -3px,
    rgb(0 0 0 / 5%) 0px 4px 6px -2px !important;
}
</style>
