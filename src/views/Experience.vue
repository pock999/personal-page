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
                  <ul style="display: flex; justify-content: flex-start;"
                  v-for="(ele) in item.doThings"
                  :key="ele">
                    <li v-text="ele"></li>
                  </ul>
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
                <ul style="display: flex; justify-content: flex-start;"
                v-for="(ele) in item.doThings"
                :key="ele">
                  <li v-text="ele"></li>
                </ul>
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
          title: '財團法人技專校院入學測驗中心-資訊處實習助理-Java(Struts2 + Spring + hibernate + Tiles)',
          period: '2020/02-2020/06',
          doThings: ['樂齡學習網-自主帶領人的填報及審核功能',
            '樂齡學習網-部分頁面調整成RWD', '樂齡學習網-登入時新增驗證碼的功能', '樂齡學習網-網站維護'],
        },
        {
          title: '台大醫院產學合作-資訊室工讀生',
          period: '2019/07-2020/06',
          doThings: ['協助開發初診預診表單(Django)', '將開發系統部屬至測試機',
            '學習到文本清洗、OCR、NLP等知識', '協助問診機器人開發除錯'],
        },
        {
          title: '大學專題製作(Django)',
          period: '2019/01-2019/12',
          /* eslint-disable global-require */
          doThings: [
            '通過108年度科技部大專學生研究計畫(基於大數據及類神經網路分析之台灣蔬果價量預測模型平台)',
            '入圍第24屆大專校院資訊應用服務創新競賽決賽(蒔價)'],
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
