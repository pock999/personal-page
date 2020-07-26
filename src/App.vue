<template>
  <div id="app">
    <v-navigation-drawer
    v-model="mobileNav"
    absolute
    temporary
    >
      <v-list-item
      v-for="tabPage in tabPages"
      :key="tabPage.tab"
      :to="tabPage.toPage"
      link
      color="white">
        <svg style="width:24px;height:24px;"
        viewBox="0 0 24 24"
        v-if="tabPage.tab=='首頁'">
          <path fill="currentColor" d="M12,3L20,9V21H15V14H9V21H4V9L12,3Z" />
        </svg>
        <span style="line-height: 24px;">
          {{ tabPage.tab }}
        </span>
      </v-list-item>
    </v-navigation-drawer>
    <!-- icon ref:https://materialdesignicons.com/ -->
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
                  <v-btn
                  color="black"
                  @click.stop="mobileNav = !mobileNav">
                    <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                      <path fill="currentColor"
                      d="M6,13H18V11H6M3,6V8H21V6M10,18H14V16H10V18Z"/>
                    </svg>
                  </v-btn>
                  {{ currentTabPage }}
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
                  <svg style="width:24px;height:24px"
                  viewBox="0 0 24 24"
                  v-if="tabPage.tab=='首頁'">
                    <path fill="currentColor" d="M12,3L20,9V21H15V14H9V21H4V9L12,3Z" />
                  </svg>
                  <span v-else>
                    {{ tabPage.tab }}
                  </span>
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
      currentTabPage: '',
      /* eslint-disable global-require */
      avatarImg: require('@/assets/B10523004.jpg'),
      /* eslint-enable global-require */
      tabPages: [
        { tab: '首頁', toPage: '/' },
        { tab: '個人資料', toPage: '/Profile' },
        { tab: '作品集', toPage: '/Portfolio' },
      ],
      mobileNav: null,
    };
  },
  created() {
    const newTabPage = this.tabPages
      .find((tab) => tab.toPage === `/${this.$router.currentRoute.name}`);
    this.currentTabPage = Boolean(newTabPage) === false ? '' : newTabPage.tab;
  },
  watch: {
    $route(to) {
      const newTabPage = this.tabPages.find((tab) => tab.toPage === `/${to.name}`);
      if (Boolean(newTabPage) === false) {
        this.currentTabPage = '';
      } else {
        this.currentTabPage = newTabPage.tab;
      }
    },
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
