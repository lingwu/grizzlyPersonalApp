<template>
  <UIFrame
    title="this is a title just for demo"
  >
<a class="mint-cell">
   <div class="mint-cell-left"></div>
   <div class="mint-cell-wrapper">
    <div class="mint-cell-title">
       <span class="mint-cell-text">标题文字</span>
    </div>
  <div class="mint-cell-value"><span></span></div>
  </div>
  <div class="mint-cell-right"> </div>
</a>
  </UIFrame>
</template>

<script>
import { LoadMore } from 'muse-ui';
import { Cell } from 'mint-ui';
import { DefaultFrame } from 'components';
export default {
  data () {
    return {
      num: 10,
      refreshing: false,
      loading: false,
      text: 'List'
    };
  },
  components: {
    UIFrame: DefaultFrame,
    LoadMore,
    Cell
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
