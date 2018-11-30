
<template>
  <div class="newlists" id="newlists">
   <ul class="smeu">
       <li><router-link :to="{ name: 'newlists1'}">汽车</router-link></li>
       <li><router-link :to="{ name: 'newlists2'}">娱乐</router-link></li>
       <li><router-link :to="{ name: 'newlists4'}">体育</router-link></li>
    </ul>
   <vue-banner01></vue-banner01>
    <router-view></router-view>
        <div class="infinite-scroll" v-show="loading">
      <svg class="loader-circular" viewBox="25 25 50 50">
        <circle class="loader-path" cx="50" cy="50" r="10" fill="none" stroke="rgb(53, 157, 218)" stroke-width="1"></circle>
      </svg>
      <span class="infinite-scroll-text">{{tips}}</span>
    </div>
  </div>
</template>
<script>
import axios from 'axios'
import banner01 from './../components/banner01';
import newban1 from './../components/new_h01';
import newlists from './../components/newlists';
import { setTimeout } from 'timers';
import $ from 'jquery'

export default {
  name: 'user',
  data () {
    return {
      newList:[],
      REQUIRE: true,
      loading: false,
      num:0,
      tips:'努力加载中...',
      url1: '',
      isNewsMenu:false
    }
  },
  components: {
    'vue-banner01':banner01,
    'vue-newban1':newban1,
    'vue-newlists':newlists
  }
}
</script>

<style>
.nlist{
  display:block;
  text-align: center;
  text-align: center
}
.nlist li{
  display:block;
  margin-bottom:0.05rem;
  text-align: left;
  font-size: 0.16rem;
  color:#5b5b5b;
  border-bottom:1px dotted #ccc
}
.nlist li a{
  font-size: 0.16rem;
  color:#5b5b5b
}
.ntit{
  font-size: 0.14rem;
  color:#303030;
  font-weight: normal
}
.infinite-scroll{
  width: 0.5rem;
  height: 0.2rem;
  margin:0 auto;
}
.nimg img{
  width: 1rem;
  height:0.7rem;
}
.ntime{
    color: #b5b5b5;
    width: 50%;
    text-align: left;
    float:right;
}
.nname{
    color: #de4c3a;
}
.ntb{
    display: block;
    clear:both;
    overflow: hidden;
    margin-top:0.08rem;
}
.smeu{
    display: block;
    background:#9c2400;
    overflow: hidden;
    line-height: 0.36rem;
    color:#ffffff;
    width: 100%;
    display: block;
    z-index: 5;
}
.smeu li{
    width:33%;
    float:left;
    text-align: center;
    font-size:0.14rem;
}
.smeu li:nth-child(2){
    width:34%;
}
.smeu li a{
    color:#ffffff;
    border-bottom:0.01rem solid #9c2400;
    display: block;
    clear:both;
    overflow: hidden;
    font-size: 0.14rem;
}
.smeu .router-link-active{
    color:#fff;
    border-bottom:0.01rem solid #9c2400;
    background:#c79649;
}
.vrw {
    height: 96%!important;
}
.itit{
   background:#9c2400;
   color:#fff;
   line-height: 0.4rem;
   border-left: 0.03rem solid #9c2400;
}
</style>

