<template>
    <div class="my-container guanzhuzhuti-follows">

        <div class="row">
            <div class="col-8 main">
                <ul class="follows-list" >
                    <li v-for="(follow,index) in follows" >
                        <nuxt-link to="/" class="avatar">
                            <img :src="follow.userAvatar" alt="">
                        </nuxt-link>
                        <div class="info">
                            <nuxt-link to="/" class="name">{{follow.userName}}</nuxt-link>
                            <div class="meta">
                                <span>关注 5</span><span>粉丝 2</span><span>文章 1</span>
                            </div>
                            <div class="meta">写了6666字，获得了333个喜欢</div>
                        </div>
                        <a href="javascript:void(0)" class="btn btn-success followBefore":id="follow.id" @click="atteShow(follow.id)"@mouseenter="yiru2(follow.id)"@mouseleave="yichu2(follow.id)">
                            <i class="fa fa-plus-square-o" :id="'icon-'+follow.id"></i>
                            <span :id="'word-'+follow.id">关注</span>
                        </a>
                    </li>
                </ul>
                <!--<div class="find-nothing" v-if="follows.length == 0">-->
                    <!--<img src="../assets/img/find-nothing.png" alt="">-->
                    <!--<div>这里还没有内容哦</div>-->
                <!--</div>-->
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        name:'guanzhuzhuti',
        data(){
            return {
                follows:[
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1001,
                    },
                    {
//                      头像 名字 时间 我关注与否
                        userName:'八万四千',
                        userAvatar:'/tag-2.jpg',
                        followTime:'2018-02-04T11:38:14.000+08:00',
                        isfollow:true,
                        id:1002,
                    },
                    {
//                      头像 名字 时间 我关注与否
                        userName:'七岁就很屌',
                        userAvatar:'/tag-3.jpg',
                        followTime:'2018-02-01T11:38:14.000+08:00',
                        isfollow:false,
                        id:1003,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1004,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1005,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1006,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1007,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1008,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:1009,
                    },
                    {
                        userName:'因为慈悲所以冰清',
                        userAvatar:'/tag-1.jpg',
                        followTime:'2018-02-05T11:38:14.000+08:00',
                        isfollow:true,
                        id:10010,
                    },
                ],
            }
        },
        methods:{
            atteShow:function (value) {
                console.log(value)
                var btn = document.getElementById(value);
                var btnIcon = document.getElementById('icon-'+value);
                var btnWord = document.getElementById('word-'+value);
//                console.log(btnIcon.className);
                //这里预留关注的ajax的操作
                //以下操作都是在发送请求成功之后
                btn.className =  btn.className == 'btn btn-success followBefore'?'btn btn-success follow':'btn btn-success followBefore'
                btnIcon.className = btnIcon.className == 'fa fa-plus-square-o' ? 'fa fa-check':'fa fa-plus-square-o'
                btnWord.innerHTML = btnWord.innerHTML == '关注'? '已关注':'关注';
//
            },
            yiru2:function (value) {
                var btn = document.getElementById(value);
                var btnIcon = document.getElementById('icon-'+value);
                var btnWord = document.getElementById('word-'+value);
                if(btn.className == 'btn btn-success follow'){
                    btnIcon.className = 'fa fa-close';
                    btnWord.innerHTML = '取消关注'
                }

            },
            yichu2:function (value) {
                var btn = document.getElementById(value);
                var btnIcon = document.getElementById('icon-'+value);
                var btnWord = document.getElementById('word-'+value);
                if(btn.className == 'btn btn-success follow'){
                    btnIcon.className = 'fa fa-check';
                    btnWord.innerHTML = '已关注'
                }
            },
        }
    }
</script>
<style scope>
    .guanzhuzhuti-follows .row{
        padding-top: 0!important;
    }
    .guanzhuzhuti-follows .row .main{
        padding-left: 0!important;
    }
    .guanzhuzhuti-follows .row .main .follows-list li{
        border-bottom: 1px solid #ccc;
        line-height: 20px;
        padding: 20px 20px 20px 0;
        vertical-align: bottom!important;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .avatar{
        width: 52px;
        height: 52px;
        margin-top: 5px;
    }
    .guanzhuzhuti-follows .row .main .follows-list a{
        display: inline-block;
    }
    .guanzhuzhuti-follows .row .main .follows-list .follow-author{
        display: inline-block;
        vertical-align: middle;
        font-size: 15px;

    }
    .guanzhuzhuti-follows .row .main .follows-list .follow-author .username{
        margin-right: 10px;
    }
    .guanzhuzhuti-follows .row .main .follows-list .avatar{
        width: 40px;
        height: 40px;
        margin-right: 10px;
    }
    .guanzhuzhuti-follows .row .main .follows-list .follow-author .follow-time{
        color:#969696;
        font-size: 12px;
        margin-top: 2px;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .btn{
        float: right;
        box-shadow: none;
        width: 100px;
        padding: 8px 0;
        font-size: 16px;
        color:white!important;
        border-radius: 20px;

    }
    .guanzhuzhuti-follows .row .main .follows-list li .followBefore{
        background-color: #42c02e;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .follow{
        background-color: #fff;
        border-color: #969696;
        color: #969696 !important;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .followBefore:hover{
        background-color: #39ad56;
        color:white!important;
    }
    .btn span{
        margin-left: 5px;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .info{
        display: inline-block;
        max-width: 450px;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .info .name{
        font-size: 15px;
        font-weight: 700;
        color:#333;
    }
    .guanzhuzhuti-follows .row .main .follows-list li .info .meta{
        padding-top:2px;
        font-size: 12px;
        color:#969696;

    }
    .guanzhuzhuti-follows .row .main .follows-list li .info .meta span{
        margin-right: 10px;
        padding-right: 10px;
        border-right: 1px solid #969696;
    }
</style>