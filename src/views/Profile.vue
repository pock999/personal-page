<template>
  <v-row>
    <v-flex>
      <v-col>
        <v-subheader style="display:block;">學歷</v-subheader>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>國立雲林科技大學-資訊管理系 畢業</v-list-item-title>
            <v-list-item-title>國立鳳山商工-國貿科 畢業</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-col>
      <v-col>
        <v-divider/>
      </v-col>
      <v-col>
        <v-subheader style="display:block;">技能</v-subheader>
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title
            v-for="(item, index) in skills"
            :key="index"
            style="font-size: 18px; line-height: 28px;">
              {{ item }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-col>
    </v-flex>
  </v-row>
</template>

<script>
export default {
  name: 'Profile',
  data() {
    return {
      skills: ['HTML、CSS', 'JavaScript、jQuery', 'Vue.js', 'Git',
        'Python、Django', 'Java Web(Spring + Struts2 +Hibernate)'],
    };
  },
};
</script>

<style lang="scss">
.v-subheader.theme--light {
  font-size: 24px;
}
</style>
