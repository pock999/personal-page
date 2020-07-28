<template>
  <div>
    <v-container v-show="!$vuetify.breakpoint.xs">
      <v-card class="mx-auto my-12">
        <v-img
        height="300"
        :src="works.image"
        contain
        ></v-img>
        <v-card-title style="display: block;">{{ works.name }}</v-card-title>
        <v-card-text>
          <div class="my-4 subtitle-1">
            使用技術:{{ works.skills }}
          </div>
          <div>
            功能:{{ works.content }}
          </div>
        </v-card-text>
        <v-divider class="mx-4"></v-divider>
        <v-card-title>
          <v-btn :href="works.url" dark target="_blank">前往</v-btn>
        </v-card-title>
      </v-card>
    </v-container>
    <v-container v-show="$vuetify.breakpoint.xs">
      <v-card class="mx-auto">
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title class="headline">{{ works.name }}</v-list-item-title>
            <v-list-item-subtitle>使用技術:{{ works.skills }}</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-img
        :src="works.image"
        height="194"
        contain
        ></v-img>
        <v-card-text>
          <v-btn :href="works.url" dark>前往</v-btn>
        </v-card-text>
      </v-card>
    </v-container>
  </div>
</template>

<script>
// 作品單一組件
export default {
  props: ['works'],
  name: 'Works',
};
</script>

<style lang="scss">
.v-btn.v-btn--contained.theme--dark.v-size--default {
  margin: auto;
}
</style>
