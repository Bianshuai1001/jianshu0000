<template>
    <div class="aside">
        <div class="title">个人介绍</div>
        <a href="javascript:void(0)" class="function-btn"@click="showedit=!showedit">
            <i class="fa fa-pencil"></i>
            编辑
        </a>
        <transition name="fade">
            <form action=""  v-if="showedit">
                <textarea></textarea>
                <input type="button" value="保存" class="btn btn-hollow">
                <a href="javacsript:void(0)">取消</a>
            </form>
        </transition>
        <div class="description">
            <div class="js-intro" style="display: block;"></div>
        </div>
        <ul class="list user-dynamic">
            <li>
                <nuxt-link to="/">
                    <i class="fa fa-th-large"></i>
                    <span>我关注的专题/文集/连载</span>
                </nuxt-link>
            </li>
            <li>
                <nuxt-link to="/">
                    <i class=" fa fa-heart-o"></i>
                    <span>我喜欢的文章</span>
                </nuxt-link>

            </li>
        </ul>
        <!--专题和文集-->
        <div class="zhuanti">
            <div >
                <div class="title">我创建的专题</div>
                <!--<div class="clearfix"></div>-->
                <div class="new-collection-block">
                    <nuxt-link to="/">
                        <i class="fa fa-plus-square-o"></i>
                        <span>创建一个新专题</span>
                    </nuxt-link>
                </div>
            </div>
            <div>
                <div class="title">我的文集</div>
                <!--<div class="clearfix"></div>-->
                <div class="new-collection-block">
                    <i class="fa fa-book"></i>
                    <span>随笔</span>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                showedit:false,
            }
        }
    }
</script>
<style>
    .aside>a{
        display: block;
        margin-bottom: 20px;
    }
     .aside .description{
        /*position: relative;*/
        margin-bottom: 16px;
        padding: 0 0 16px;
        text-align: left;
        border-bottom: 1px solid #f0f0f0;
        clear: both;
        word-break: break-all!important;
    }
      .aside .title{
        float:left;
        margin-bottom: 10px;
        font-size: 14px;
        color: #969696 !important;
    }
      .aside .function-btn{
        float: right;
        font-size: 13px;
        color:#969696;
    }
    .user .row .aside form{
        margin-bottom: 20px;

    }
    .aside form textarea{
        width:100%;
        height:125px;
        font-size: 14px;
        margin-bottom: 5px;
        padding:5px 10px;
        border:1px solid #ccc;
        border-radius: 4px;
        display:inline-block;
        vertical-align: top;
        outline-style: none;
        resize: none;
        font-size:13px;
    }
     .aside form input{
        padding:5px 20px;
        font-size: 14px;
        border: 1px solid #42c02e;
        background-color: #fff;
        color: #42c02e !important;
        border-radius: 20px;
    }
      .aside form a{
        margin-left: 10px;
        font-size: 14px;
        color:#969696;
        vertical-align: middle;
        line-height: 34px;
    }
      .aside .user-dynamic{
        padding-bottom:6px;
    }
      .aside .list{
        margin-bottom: 16px;
        border-bottom: 1px solid #f0f0f0;
    }
      .aside .list li a{
        display: inline-block;
        font-size: 14px;
        color: #333333 !important;
        line-height: 30px;
        vertical-align: middle;
        margin: 6px 0;
    }
      .aside .list li a i{
        font-size: 22px;
        margin-right: 10px;
        line-height: 30px;
        vertical-align: middle;
    }
     .aside .zhuanti .new-collection-block {
        position: relative;
        margin-bottom: 16px;
        padding: 0 0 16px;
        text-align: left;
        /*font-size: 0;*/
        border-bottom: 1px solid #f0f0f0;
        clear: both;
        word-break: break-all!important;
    }
     .aside .zhuanti .new-collection-block span{
        font-size: 14px;
    }
     .aside .zhuanti .new-collection-block a{
        font-size: 13px;
        color: #42c02e!important;
    }
     .aside .zhuanti .new-collection-block i{
        margin-right: 10px;
    }
      .aside .zhuanti .new-collection-block>i{
        color: #969696 !important;
    }
</style>