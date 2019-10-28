<template>
  <!-- 不同分类的具体信息首 -->
  <section class="m-istyle">
    <dl>
      <dt>有格调</dt>
      <dd
        @mouseover="over"
        :class="{active:kind==='all'}"
        kind="all"
        keyword="景点">全部</dd>
      <dd
        @mouseover="over"
        :class="{active:kind==='part'}"
        kind="part"
        keyword="美食">约会聚餐</dd>
      <dd
        @mouseover="over"
        :class="{active:kind==='spa'}"
        kind="spa"
        keyword="丽人">丽人SPA</dd>
      <dd
        @mouseover="over"
        :class="{active:kind==='movie'}"
        kind="movie"
        keyword="电影">电影演出</dd>
      <dd
        @mouseover="over"
        :class="{active:kind==='travel'}"
        kind="travel"
        keyword="旅游">品质出游</dd>
    </dl>
    <ul class="ibody">
      <li
        v-for="(item ,index) in cur"
        :key="index">
        <el-card
          :body-style="{ padding: '0px' }"
          shadow="never">
          <img
            :src="item.img"
            class="image">
          <ul class="cbody">
            <li class="title">{{ item.title }}</li>
            <li class="pos" :title="item.pos"><span>{{ item.pos }}</span></li>
            <li class="price">￥<em>{{ item.price }}</em><span>/起</span></li>
          </ul>
        </el-card>
      </li>
    </ul>
  </section>
  <!-- 不同分类的具体信息尾 -->
</template>
<script>
export default {
  data: () => {
    return {
      kind: 'all',
      list: {
        all: [{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          },{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          },{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          },{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          },{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          },{
            img:'//p1.meituan.net/bbia/fe77a0788d56d9a735c5691bbc2787db90142.jpg@368w_208h_1e_1c',
            title:'36 MATCHART·生日蛋糕（皇庭广场店）',
            pos:'【全网热销】芒果流心/海盐流心（2选1）爆浆生日蛋糕1个，约2磅，圆形',
            price:138
          }
        ],
        part: [{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          },{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          },{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          },{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          },{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          },{
            img:'//p0.meituan.net/msmerchant/a56c4d4082a7b662f19c4b9a6eb56c622342599.jpg@368w_208h_1e_1c',
            title:'必胜客（中心城店）',
            pos:'美式精选比萨（芝心普通装）+超牛联盟牛排拼盘1份',
            price:105.5
          }
        ],
        spa: [{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },{
            img:'//p1.meituan.net/wedding/40f4f3301a12cd63e63eb4abc7ce44641099389.jpg@240w_180h_1e_1c_1l|watermark=1&&r=2&p=9&x=2&y=2&relative=1&o=20|368w_208h_1e_1c',
            title:'百丽雅SPA三养美容会所（购物公园店）',
            pos:'百丽雅SPA三养美容会所（购物公园店）',
            price:157
          },
        ],
        movie: [{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },{
            img:'//p1.meituan.net/poi/030e784b22a578d15c59cc5c0d3824b71081344.jpg@368w_208h_1e_1c',
            title:'万达影城（海雅广场店）',
            pos:'免押金,可停车,可刷卡,休息区,儿童票,real D厅,IMAX厅,RealD 6FL厅',
            price:50
          },
        ],
        travel: [{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },{
            img:'//p1.meituan.net/tdchoteldark/63c33d443879575b0d2aa881af10dfc65574161.jpg@368w_208h_1e_1c',
            title:'麗枫酒店',
            pos:'预约发票，房间内消费品，免押金，酒店套餐',
            price:500
          },
        ]
      }
    }
  },
  //获取不同类别中的数据
  computed: {
    cur: function () {
      return this.list[this.kind]
    }
  },
  methods: {
    //修改kind
    over:function(e){
      this.kind=e.target.getAttribute('kind');
    }
  },

}
</script>
<style lang="scss">
    @import "@/assets/css/index/artistic.scss";
</style>
