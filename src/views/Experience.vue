<template>
  <div>
    <v-container>
      <v-timeline v-show="!$vuetify.breakpoint.xs">
        <v-timeline-item
        fill-dot="fillDot"
        icon-color="iconColor"
        v-for="(item) in experienceList"
        :key="item">
          <v-card class="elevation-2">
            <v-card-title class="headline">{{ item.title }}</v-card-title>
            <v-card-text>
              {{ item.period }}
              <v-list-item fill-dot="false">
                <v-list-item-content>
                  <v-list-item-title
                  style="display: flex; justify-content: flex-start;"
                  v-for="(ele) in item.doThings"
                  :key="ele">
                    - {{ ele }}
                  </v-list-item-title>
                </v-list-item-content>
              </v-list-item>
            </v-card-text>
          </v-card>
        </v-timeline-item>
      </v-timeline>
      <v-cantainer v-show="$vuetify.breakpoint.xs">
        <v-card class="elevation-2"
        style="margin-bottom: 5px;"
        v-for="(item) in experienceList"
        :key="item">
          <v-card-title class="headline">{{ item.title }}</v-card-title>
          <v-card-text>
            {{ item.period }}
            <v-list-item fill-dot="false">
              <v-list-item-content>
                <v-list-item-title
                style="display: flex; justify-content: flex-start;"
                v-for="(ele) in item.doThings"
                :key="ele">
                  - {{ ele }}
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-card-text>
        </v-card>
      </v-cantainer>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Experience',
  data() {
    return {
      experienceList: [
        {
          title: '財團法人技專校院入學測驗中心-資訊處實習助理',
          period: '2020/02-2020/06',
          doThings: ['thing1', 'thing2'],
        },
        {
          title: '台大醫院產學合作-資訊室工讀生',
          period: '2019/07-2020/06',
          doThings: ['thing1', 'thing2', 'thing3'],
        },
        {
          title: '大學專題製作(蒔價/基於大數據及類神經網路分析之台灣蔬果價量預測模型平台)',
          period: '2019/01-2019/12',
          /* eslint-disable global-require */
          doThings: ['通過108年度科技部大專學生研究計畫',
            '入圍第24屆大專校院資訊應用服務創新競賽決賽'],
          /* eslint-enable global-require */
        },
      ],
    };
  },
};
</script>

<style lang="scss">
.theme--light.v-timeline:before {
  background: #333333;
}
.v-timeline-item__inner-dot {
  background: #eeeeee;
  border: #333333 5px solid;
}
.theme--light.v-timeline .v-timeline-item .v-card {
  &:before, &:after {
    display: none;
  }
}
</style>
