<template>
    <div class="my-container chats">
        <my-header></my-header>
        <div class="row">
            <div class="col-4 ">
                <LeftMenu></LeftMenu>
            </div>
            <div class="col-8 main">
                <div class="menu">全部简信</div>
                <div class="comment-placeholder" style="display:none;">
                    <div class="author">
                        <div class="avatar"></div>
                        <div class="info">
                            <div class="name"></div>
                            <div class="meta"></div>
                        </div>
                    </div>
                    <div class="title"></div>
                    <div class="title animated-delay"></div>
                    <div class="tool-group">
                        <i class="fa fa-thumbs-up"></i>
                        <div class="zan"></div>
                        <i class="fa fa-comment"></i>
                        <div class="zan"></div>
                    </div>
                </div>
                <ul class="jianxin-list" v-for="jianxin in jianxins">
                    <li>
                        <div class="pull-right">
                            <span @click="showMenu = !showMenu">{{jianxin.jianxinTime|time}}<i class="fa fa-angle-down"></i></span>
                            <ul class="down-menu" v-if="showMenu">
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa-trash"></i>
                                        删除会话
                                    </nuxt-link>
                                </li>
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-ban"></i>
                                        加入黑名单
                                    </nuxt-link>

                                </li>
                                <li>
                                    <nuxt-link to="/">
                                        <i class="fa fa-flag-o"></i>
                                        举报用户
                                    </nuxt-link>
                                </li>
                            </ul>
                        </div>
                        <nuxt-link to="/u/123" class="avatar">
                            <img :src="jianxin.jianxinAvatar" alt="">
                        </nuxt-link>
                        <nuxt-link to="/" class="name">{{jianxin.jianxinName}}</nuxt-link>
                        <nuxt-link to="/" class="jianxin-info">
                            <p class="text">{{jianxin.jianxinLink}}</p>
                        </nuxt-link>
                    </li>
                </ul>
                <div class="find-nothing" v-if="jianxins.length==0">
                    <img src="../../assets/img/find-nothing.png" alt="">
                    <div>这里还没有内容哦</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import LeftMenu from '~/components/LeftMenu'
    import myHeader from '~/components/myHeader'
    import NuxtLink from "../../.nuxt/components/nuxt-link";
    export default {
        data(){
            return{
                jianxins:[
                    {
//                        头像  名字  链接  时间
                        jianxinName:'风雪之人',
                        jianxinAvatar:'/tag-1.jpg',
                        jianxinLink:'欢迎加入丰富多彩的原创内容社区—简书欢迎加入丰富多彩的原创内容社区迎加入丰富多彩的原创内容社区',
                        jianxinTime:'2018-02-05T11:38:14.000+08:00',
                    }
                ],
                showMenu:false,
            }
        },
        components:{
            NuxtLink,
            LeftMenu,
            myHeader
        }
    }
</script>
<style>
    .chats .row{
        padding:30px 0;
    }
    .chats .row .main .menu{
        margin-bottom:20px;
        font-size: 14px;
        font-weight: 700;
    }
    .chats .row .main .jianxin-list .avatar{
        width: 48px;
        height: 48px;
        display: block;
        margin: 20px 10px 20px 20px;
        float: left;
    }
    .chats .row .main .jianxin-list .jianxin-info{
        display: block;
        padding:20px 20px 20px 0;
        min-height: 88px;
        vertical-align: middle;
        /*float:left;*/
    }
    .chats .row .main .jianxin-list>li{
        border-top: 1px solid #f0f0f0;
        position: relative;
        line-height: 20px;
    }
    .chats .row .main .jianxin-list>li .name{
        position: absolute;
        top:25px;
        font-size: 15px;
    }
    .chats .row .main .jianxin-list .jianxin-info .text{
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        font-size: 12px;
        color: #ccc !important;
        margin:0;
        width: 50%;
        /*position: absolute;*/
        font-size: 14px;
        margin: 28px 0 0 ;
    }
    .chats .row .main .jianxin-list .pull-right{
        float: right;
        color:#9b9b9b;
        margin: 20px 20px 0 0;
        font-size: 13px;
    }
    .chats .row .main .jianxin-list .pull-right .down-menu{
        padding:5px 0;
        margin: 2px 0 0;
        float: right;
        position: absolute;
        z-index: 1000;
        background-color: #fff;
        text-align: left;
        border-radius: 4px;
        box-shadow: 0 2px 8px rgba(0,0,0,.1);
        border: 1px solid #ccc;
    }
    .chats .row .main .jianxin-list .pull-right .down-menu li{
        width: 100%;
    }
    .chats .row .main .jianxin-list .pull-right .down-menu a{
        display: inline-block;
        padding: 10px 20px;
        text-align: left;
        color:#2f2f2f;
        width: 100%;
    }
    .chats .row .main .jianxin-list .pull-right .down-menu a i{
        margin-right: 2px;
    }
    .chats .row .main .jianxin-list .pull-right .down-menu a:hover{
        background-color: #f0f0f0;
    }
</style>
