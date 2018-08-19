<template>
  <UIFrame
    title="关于我们"
  >
  <div class="mu-card">
   <div class="mu-card-media">
    <img src="../../assets/images/schoolLogo.png" />
   </div>
   <div class="mu-card-text">
     {{appCon}}
   </div>
  </div>
  <a class="mint-cell" v-for='lists in list'>
    <span class="mint-cell-mask"></span>
    <div class="mint-cell-left"></div>
    <div class="mint-cell-wrapper">
      <div class="mint-cell-title">
        <span class="mint-cell-text">{{lists.title}}</span>
      </div>
      <div class="mint-cell-value is-link">
        <span>{{lists.con}}</span>
      </div>
      <i class="mint-cell-allow-right"></i>
    </div>
    <div class="mint-cell-right"></div>
  </a>
  </UIFrame>
</template>

<script>
import { LoadMore,Card } from 'muse-ui';
import { Cell } from 'mint-ui';
import { DefaultFrame } from 'components';
export default {
  data () {
    return {
      num: 10,
      refreshing: false,
      loading: false,
      text: 'List',
      list:[
       {title:'软件版本',con:'1.2.3'},
       {title:'客服电话',con:'400-620-4520'},
       {title:'客服电话',con:'www.dhxhr.com'},
       {title:'隐私条款',con:'www.dhxhr.com'}
      ],
      appCon:'大灰熊科技大灰熊科技大灰熊科技大灰熊科技大灰熊科技大灰熊科技  大灰熊科技大灰熊科技大灰熊科技大灰熊科技大灰熊科技大灰熊科技'
    };
  },
  components: {
    UIFrame: DefaultFrame,
    LoadMore,
    Cell,
    Card
  },
  methods: {
    refresh () {
      this.refreshing = true;
      this.$refs.container.scrollTop = 0;
      setTimeout(() => {
        this.refreshing = false;
        this.text = this.text === 'List' ? 'Menu' : 'List';
        this.num = 10;
      }, 2000);
    },
    load () {
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
        this.num += 10;
      }, 2000);
    }
  },
  mounted () {
  }
};
</script>
<style lang="less" scoped>
@import url('../../assets/css/base.less');
</style>
