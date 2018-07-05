<template>
  <div>
    <div
      class="item"
      v-for="(item, index) of list"
      :key="index"
    >
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 .2rem
    .item-title-icon
      display: inline-block
      width: .36rem
      height: .36rem
      background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAflBMVEUAAAD/bm7/b2//b2//eXn/b2//b2//bm7/b2//b2//bm7/b2//b2//b2//bm7/b2//b2//cXH/eHj/qqr/bm7/////cXH/iIj/oqL//f3/mJj/fHz/9/f/8PD/4eH/ycn/6+v/1dX/0ND/t7f/ra3/kpL/jo7/c3P/5ub/vr7o37bEAAAAFHRSTlMA9uZeCfny7NvLt6+PfGZONxsRA/pz1k8AAAFrSURBVEjHpZbZdoMwDERtMEvYE8YJZN/b/v8PNvicJsiYqJzcB548WGNZksUAVWZJHAVBFCdZqQTDwk8lesjUX4hxVB5iQJiPbVMXHpx4RS0czGcYZTYXAyoPb/AqYeFLvEX61nqwEEUlwSKrnl9X/JtmZfl4Oq9d53Pfan2yzurvdAs42OsHaxAKYVDOA207wcEKShlBDhfaIUBu7lsIl2UjuIASLkZTsDaCxpWMFC7ORrCBRfqw7MxZY9Z/w0YqUWLI8tLqJ+25n8BSZP3Am+aG2/Vw1IQ9XmQiwZNV9z+0mkKtJCKmAg094IgXsYg4Ab0gkQh4wRUvgv8I1kTAh7QHCYk3fQIxnbCCHXokImMFPyCJKznB9gvkaijJ7XCnl0+kU3ZISQFttp3DnWW5oQVES3S57D4Eq0RJE+DJSZvh8RRpZDwFaZU8s5o0YxZvPrXdTx0on40sfih+Nnb5wT7x6fDR42Ty8+cXnHyOvDgQEbUAAAAASUVORK5CYII=')
      margin-right: .1rem
      background-size: .4rem 3rem
  .item-children
    padding: 0 .2rem
</style>
