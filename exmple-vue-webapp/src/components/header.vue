<template>
    <header class="app-header" :style="{background:headerBg,color:titleColor}" :class="{ 'header-table': titleBg}">
      <p class="h-left">
        <slot name="left"></slot>
      </p>
      <h1 class="app-title">{{title}}</h1>
      <p class="h-right">
        <slot name="right"></slot>
      </p>
    </header>
</template>

<script>
    export default {
        data() {
         return{
           isB :true
         }
        },
        props:{
          title:String,
          titleColor:String,
          headerBg:String,
          titleBg:Boolean
        }
    }
</script>

<style lang="scss">

    body .header-table{
      background-color: #eee;
      color:#333;
    }
   .app-header{
      position: relative;
      padding: 0 10px;
      -webkit-box-sizing: border-box;
      box-sizing: border-box;
      height: 45px;
      line-height: 45px;
      background:#1D1A1A;
      color:#f2f2f2;

      .h-left,.h-right{
        position: absolute;
        top:0;
        width: 82px;
        text-align: center;
        font-size: 15px;
        z-index:100;
        i{
          vertical-align: -1px;
        }
        a{
          color:#fdfdfd;
        }
      }

      .h-left{
        left: 0;
      }

      .h-right{
        right: 0;
      }

      .app-title{
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        padding:0 5px;
        text-align: center;
        font-size: 18px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;

      }
   }
</style>