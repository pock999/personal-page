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
              <v-list-item v-show="!$vuetify.breakpoint.xs">
                <v-list-item-content class="top-info">
                  <v-list-item-title >侯柏超 Rick</v-list-item-title>
                  <v-list-item-subtitle style="color:white;">
                    <a href="mailto:hpx210650@gmail.com" class="icon-link">
                      <svg style="width:32px;height:32px" viewBox="0 0 24 24">
                        <path fill="currentColor"
                        d="M22,6V4L14,9L6,4V6L14,11L22,6M22,2A2,
                        2 0 0,1 24,4V16A2,2 0 0,1 22,18H6C4.89,
                        18 4,17.1 4,16V4C4,2.89 4.89,2 6,2H22M2,
                        6V20H20V22H2A2,2 0 0,1 0,20V6H2Z" />
                      </svg>
                      <span>&nbsp;hpx210650@gmail.com</span>
                    </a>
                  </v-list-item-subtitle>
                  <v-list-item-subtitle>
                    <a href="https://github.com/pock999" class="icon-link" target="_blank">
                      <svg style="width:36px;height:36px" viewBox="0 0 24 24">
                        <path fill="currentColor"
                        d="M12,2A10,10 0 0,0 2,12C2,16.42 4.87,
                        20.17 8.84,21.5C9.34,21.58 9.5,21.27 9.5,
                        21C9.5,20.77 9.5,20.14 9.5,19.31C6.73,
                        19.91 6.14,17.97 6.14,17.97C5.68,
                        16.81 5.03,16.5 5.03,16.5C4.12,15.88 5.1,15.9 5.1,
                        15.9C6.1,15.97 6.63,16.93 6.63,16.93C7.5,
                        18.45 8.97,18 9.54,17.76C9.63,17.11 9.89,16.67 10.17,
                        16.42C7.95,16.17 5.62,15.31 5.62,11.5C5.62,10.39 6,
                        9.5 6.65,8.79C6.55,8.54 6.2,7.5 6.75,6.15C6.75,
                        6.15 7.59,5.88 9.5,7.17C10.29,6.95 11.15,6.84 12,
                        6.84C12.85,6.84 13.71,6.95 14.5,7.17C16.41,5.88 17.25,
                        6.15 17.25,6.15C17.8,7.5 17.45,8.54 17.35,8.79C18,
                        9.5 18.38,10.39 18.38,11.5C18.38,15.32 16.04,
                        16.16 13.81,16.41C14.17,16.72 14.5,17.33 14.5,
                        18.26C14.5,19.6 14.5,20.68 14.5,21C14.5,21.27 14.66,21.59 15.17,
                        21.5C19.14,20.16 22,16.42 22,12A10,10 0 0,0 12,2Z" />
                      </svg>
                      <span>&nbsp;https://github.com/pock999</span>
                    </a>
                  </v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
              <v-list-item v-show="$vuetify.breakpoint.xs">
                <v-list-item-content class="top-info">
                  <v-list-item-title >侯柏超 Rick</v-list-item-title>
                  <v-list-item-subtitle style="color:white;">
                    <a href="mailto:hpx210650@gmail.com" class="icon-link">
                      <svg style="width:32px;height:32px" viewBox="0 0 24 24">
                        <path fill="currentColor"
                        d="M22,6V4L14,9L6,4V6L14,11L22,6M22,2A2,
                        2 0 0,1 24,4V16A2,2 0 0,1 22,18H6C4.89,
                        18 4,17.1 4,16V4C4,2.89 4.89,2 6,2H22M2,
                        6V20H20V22H2A2,2 0 0,1 0,20V6H2Z" />
                      </svg>
                    </a>
                    <a href="https://github.com/pock999" class="icon-link" target="_blank">
                      <svg style="width:36px;height:36px" viewBox="0 0 24 24">
                        <path fill="currentColor"
                        d="M12,2A10,10 0 0,0 2,12C2,16.42 4.87,
                        20.17 8.84,21.5C9.34,21.58 9.5,21.27 9.5,
                        21C9.5,20.77 9.5,20.14 9.5,19.31C6.73,
                        19.91 6.14,17.97 6.14,17.97C5.68,
                        16.81 5.03,16.5 5.03,16.5C4.12,15.88 5.1,15.9 5.1,
                        15.9C6.1,15.97 6.63,16.93 6.63,16.93C7.5,
                        18.45 8.97,18 9.54,17.76C9.63,17.11 9.89,16.67 10.17,
                        16.42C7.95,16.17 5.62,15.31 5.62,11.5C5.62,10.39 6,
                        9.5 6.65,8.79C6.55,8.54 6.2,7.5 6.75,6.15C6.75,
                        6.15 7.59,5.88 9.5,7.17C10.29,6.95 11.15,6.84 12,
                        6.84C12.85,6.84 13.71,6.95 14.5,7.17C16.41,5.88 17.25,
                        6.15 17.25,6.15C17.8,7.5 17.45,8.54 17.35,8.79C18,
                        9.5 18.38,10.39 18.38,11.5C18.38,15.32 16.04,
                        16.16 13.81,16.41C14.17,16.72 14.5,17.33 14.5,
                        18.26C14.5,19.6 14.5,20.68 14.5,21C14.5,21.27 14.66,21.59 15.17,
                        21.5C19.14,20.16 22,16.42 22,12A10,10 0 0,0 12,2Z" />
                      </svg>
                    </a>
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
              fixed-tabs
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
        { tab: '經歷', toPage: '/Experience' },
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
.icon-link {
  color: white;
  margin-right: 3px;
  margin-left: 3px;
  text-decoration: none;
  &:hover {
    color: #bbbbbb;
  }
  span {
    font-size: 18px;
    line-height: 36px;
    vertical-align: top;
  }
}
</style>
