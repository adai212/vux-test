<i18n>
hello:
  en: hello
  zh-CN: 你好
</i18n>
<template>
  <div id="app">
  	<label for="locale">locale</label>
    <select v-model="locale">
      <option>en</option>
      <option>zh-CN</option>
    </select>
  	<p>{{ $t('hello') }}</p>
  	<p>{{ $t('world') }}</p>
    <router-view></router-view>
  </div>
</template>

<script>
import Vue from 'vue'
export default {
  name: 'app',
  data () { return { locale: 'zh-CN' } },
	watch: {
	  locale (val) {
	    Vue.i18n.set(val)
	  }
	}
}
</script>

<style lang="less">
@import '~vux/src/styles/reset.less';

body {
  background-color: #fbf9fe;
}
</style>
