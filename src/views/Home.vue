<template>
  <div class="home">
    <v-container fill-height fluid>
      <v-row>
        <v-flex>
          <v-col justify="center" align="center">
          <vue-typer
          :text='["Hello 你好!","歡迎來到我的個人頁"]'
          :repeat='Infinity'
          :shuffle='false'
          initial-action='typing'
          :pre-type-delay='70'
          :type-delay='70'
          :pre-erase-delay='2000'
          :erase-delay='250'
          erase-style='select-all'
          :erase-on-complete='false'
          caret-animation='blink'
          />
          </v-col>
        </v-flex>
      </v-row>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue';
// https://www.npmjs.com/package/vue-typer
// https://cngu.github.io/vue-typer/#style-showcase
import { VueTyper } from 'vue-typer';

export default {
  name: 'Home',
  components: {
    'vue-typer': VueTyper,
  },
};
</script>
<style lang="scss" scoped>
.home {
  margin-top: 100px;
}
.vue-typer {
  font-size: 2.5em;
}
</style>
