<template>
  <div id="app">
    <div class="top">
      <v-container fill-height fluid>
        <v-row>
          <v-flex>
            <v-col justify="center" align="center">
              <v-avatar
                class="profile"
                color="grey"
                size="125"
                tile
              >
                <v-img :src="avatarImg"></v-img>
              </v-avatar>
              <v-list-item>
                <v-list-item-content class="top-info">
                  <v-list-item-title >侯柏超</v-list-item-title>
                  <v-list-item-subtitle style="color:white;">
                    國立雲林科技大學 資訊管理系 畢業
                  </v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-col>
          </v-flex>
        </v-row>
      </v-container>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      /* eslint-disable global-require */
      avatarImg: require('@/assets/B10523004.jpg'),
      /* eslint-enable global-require */
    };
  },
};
</script>

<style lang="scss">
// <router-link to="/">Home</router-link>
.top {
  background-color: black;
  height: 300px;
  width: 100%;
  color: white;
}
.top-info{
  color: white;
}
#app {
  font-family: "微軟正黑體", Helvetica, Arial, sans-serif;
}
</style>
