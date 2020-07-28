<template>
  <div>
    <v-container>
      <v-flex>
        <v-col>
          <Works v-for="(item) in portfolioList" :works="item" :key="item" />
        </v-col>
      </v-flex>
    </v-container>
  </div>
</template>

<script>
import Works from '../components/Works.vue';

export default {
  name: 'Portfolio',
  components: {
    Works,
  },
  data() {
    return {
      portfolioList: [
        {
          name: 'Vue口罩地圖',
          url: 'https://pock999.github.io/vue-mask-map/',
          image: 'https://github.com/pock999/vue-mask-map/raw/master/demo/demo.gif',
          skills: 'Ajax(axios、VueAxios)、Vue 組件溝通(Props, Emit)、Vue watch、 Vue lifecycle',
          content: '獲取資料並顯示至地圖上、選擇縣市及鄉鎮市區、地圖移動至該地區、一開始可以依據使用者位置定位',
        },
        {
          name: 'Vue組件-購物車',
          url: 'https://pock999.github.io/vue-shopcart/',
          image: 'https://raw.githubusercontent.com/pock999/vue-shopcart/master/demo-img/demo.gif',
          skills: 'Vue 組件溝通(Props, Emit)、嘗試使用SCSS',
          content: '加入購物車、增減數量、移除項目、庫存為0加入購物車的按鈕會變成"沒有庫存了"',
        },
        {
          name: 'Vue-TodoList',
          url: 'https://pock999.github.io/vue-todolist/',
          image: 'https://raw.githubusercontent.com/pock999/vue-todolist/master/demo-img/todolist-demo.gif',
          skills: 'Vue 組件溝通(Props, Emit)',
          content: '新增、點一下完成(取消完成)、更改、刪除',
        },
        {
          name: '專題',
          url: 'https://github.com/pock999/ProjectExplanation',
          image: 'https://raw.githubusercontent.com/pock999/ProjectExplanation/master/screenshot/home.jpg',
          skills: 'Python(Ta-Lib、NumPy、Pandas)、JavaScript、jQuery、Django、SQLite、Chart.js',
          content: '列出作物清單畫面、作物搜尋畫面、作物資料畫面(RSI、KD指標、MACD、布林通道等金融指標以及時間序列分析)',
        },
      ],
    };
  },
};
</script>

<style lang="scss">

</style>
