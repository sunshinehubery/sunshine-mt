<template>
    <div class="search-panel">
        <el-row class="m-header-searchbar">
            <el-col :span="3" class="left">
                <img
                src="//s0.meituan.net/bs/fe-web-meituan/e5eeaef/img/logo.png"
                alt="美团">
            </el-col>
            <el-col :span="15" class="center">
                <div class="wrapper">
                     <el-input 
                        v-model="search"
                        placeholder="搜索商家或地点"
                        @focus="focus"
                        @blur="blur"
                        @input="input"
                    />
                     <button class="el-button el-button--primary"><i class="el-icon-search"/></button>
                     <dl class="hotPlace" v-if="isHotPlace">
                        <dt>热门搜索</dt>
                        <dd v-for="(item, index) in hotPlace" :key="index">{{item}}</dd>
                     </dl>
                     <dl class="searchList" v-if="isSearchList">
                        <dd v-for="(item, index) in searchList" :key="index">{{item}}</dd>
                     </dl>
                </div>
                <p class="suggest">
                    <nuxt-link to="/">故宫博物院</nuxt-link>
                    <nuxt-link to="/">故宫博物院</nuxt-link>
                    <nuxt-link to="/">故宫博物院</nuxt-link>
                    <nuxt-link to="/">故宫博物院</nuxt-link>
                    <nuxt-link to="/">故宫博物院</nuxt-link>
                </p>
                <ul class="nav">
                    <li><nuxt-link
                        to="/"
                        class="takeout">美团外卖</nuxt-link></li>
                    <li><nuxt-link
                        to="/"
                        class="movie">猫眼电影</nuxt-link></li>
                    <li><nuxt-link
                        to="/"
                        class="hotel">美团酒店</nuxt-link></li>
                    <li><nuxt-link
                        to="/"
                        class="apartment">民宿/公寓</nuxt-link></li>
                    <li><nuxt-link
                        to="/"
                        class="business">商家入驻</nuxt-link></li>
                </ul>
            </el-col>
            <el-col :span="6" class="right">
                <ul class="security">
                    <li><i class="refund"/><p class="txt">随时退</p></li>
                    <li><i class="single"/><p class="txt">不满意免单</p></li>
                    <li><i class="overdue"/><p class="txt">过期退</p></li>
                </ul>
            </el-col>
        </el-row>
    </div>
</template>
<<script>
    export default {
        data() {
            return {
                search:'',
                isFocus: false,
                hotPlace: ['火锅','火锅','火锅'],
                searchList: ['干锅','干锅','干锅','干锅','干锅'],
            }
        },
        computed: {
            //开启热门搜索
            isHotPlace:function(){
                return this.isFocus&&!this.search;
            },
            //开启搜索列表
            isSearchList:function(){
                return this.isFocus&&this.search;
            }
        },
        methods: {
            //点击搜索框
            focus:function(){
                this.isFocus=true;
            },
            //搜索框失去焦点   
            blur:function(){
                let self = this;
                setTimeout(function(){
                    self.isFocus=false;
                },200);
            },
            input:function(){
                console.log("input");
            }
        },
    }
</script>
<style lang="scss">
    @import "@/assets/css/public/header/search.scss";
</style>