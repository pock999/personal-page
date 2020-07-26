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
                  <v-list-item-title >侯柏超 Rick</v-list-item-title>
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
    <v-container fill-height fluid>
      <v-row>
        <v-flex>
          <v-col justify="center" align="center">
            <v-card style="max-width:960px;">
              <v-toolbar flat color="primary"
              v-show="$vuetify.breakpoint.xs"
              dark>
                <v-toolbar-title>
                  <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                    <path fill="currentColor"
                    d="M5,15.5L7.5,20H2.5L5,15.5M9,19H21V17H9V19M5,9.5L7.5,
                    14H2.5L5,9.5M9,13H21V11H9V13M5,3.5L7.5,8H2.5L5,3.5M9,7H21V5H9V7Z"
                    />
                  </svg>
                </v-toolbar-title>
              </v-toolbar>
              <v-tabs
              background-color="primary"
              dark
              v-show="!$vuetify.breakpoint.xs"
              >
                <v-tab
                v-for="tabPage in tabPages"
                :key="tabPage.tab"
                :to="tabPage.toPage"
                >
                  {{ tabPage.tab }}
                </v-tab>
              </v-tabs>
              <router-view/>
            </v-card>
          </v-col>
        </v-flex>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      /* eslint-disable global-require */
      avatarImg: require('@/assets/B10523004.jpg'),
      /* eslint-enable global-require */
      tabPages: [
        { tab: 'Home', toPage: '/' },
        { tab: '個人資料', toPage: '/Profile' },
      ],
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
