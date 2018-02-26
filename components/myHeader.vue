<template>
    <div>
        <nav class="navbar navbar-default navbar-fixed-top">
            <div class="width-limit">
                <!--logo-->
                <nuxt-link to="/" class="nav-logo">
                    <img src="../assets/img/nav-logo.png" alt="" >
                </nuxt-link>
                <!--写文章-->
                <nuxt-link to="/create" class="btn write-btn">
                    <i class="fa fa-edit"></i>
                    写文章
                </nuxt-link>
                <!--登录和注册按钮-->
                <nuxt-link v-if="!showAvatar" to="sign-up" class="btn sign-up">注册</nuxt-link>
                <nuxt-link v-if="!showAvatar" to="sign-in" class="btn sign-in">登录</nuxt-link>
                <!--如果用户登录了，那么显示用户头像-->
                <div v-if="showAvatar" class="user" @mouseover="userShow=true" @mouseleave="userShow=false">
                    <div class="drop-down">
                        <nuxt-link class="avatar" to="/users">
                            <img src="../assets/img/user.jpg" alt="">
                        </nuxt-link>
                    </div>
                    <div class="drop-menu" v-show="userShow">
                        <ul>
                            <li>
                                <nuxt-link to="/u/123">
                                    <i class="fa fa-home"></i>
                                    我的主页
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/bookmarks">
                                    <i class="fa fa-bookmark"></i>
                                    收藏的文章
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/u/123/liked_notes">
                                    <i class="fa fa-heart"></i>
                                    喜欢的文章
                                </nuxt-link>
                            </li>
                            <li>
                                <nuxt-link to="/settings/basic" @click="showAvatar = !showAvatar">
                                    <i class="fa fa-cog"></i>
                                    设置
                                </nuxt-link>
                            </li>
                            <li @click="signOut">
                                <nuxt-link to="/">
                                    <i class="fa fa-sign-out"></i>
                                    退出
                                </nuxt-link>
                            </li>
                        </ul>
                    </div>
                </div>
                <!--导航-->
                <div class="my-container">
                    <ul class="nav-list">
                        <li class=" hover" :class="{active:this.$route.path == '/'}" >
                            <nuxt-link to="/" >
                                <i class="fa fa-compass noshow"></i>
                                <span>发现</span>
                            </nuxt-link>
                        </li>
                        <li class="hover" :class="{active:this.$route.path == '/subscriptions'}">
                            <nuxt-link to="/subscriptions">
                                <i class="fa fa-book noshow"></i>
                                <span>关注</span>
                            </nuxt-link>
                        </li>
                        <li class="info-down hover"@mouseover="infoShow=true" @mouseleave="infoShow=false"
                            :class="{active:this.$route.path == '/notifications/comments'
                            |this.$route.path == '/notifications/chats'
                            |this.$route.path =='/notifications/requests'
                            |this.$route.path =='/notifications/likes'
                            |this.$route.path == '/notifications/follows'}">
                            <nuxt-link to="/notifications/comments">
                                <i class="fa fa-bell-o noshow"></i>
                                <span>消息</span>
                            </nuxt-link>
                            <div class="info-menu" v-show="infoShow">
                                <ul>
                                    <li>
                                        <nuxt-link to="/notifications/comments">
                                            <i class="fa fa-comment-o"></i>
                                            <span>评论</span>
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/notifications/chats">
                                            <i class="fa fa-envelope-o"></i>
                                            <span>简信</span>
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/notifications/requests">
                                            <i class="fa fa-upload"></i>
                                            <span>投稿请求</span>
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/notifications/likes">
                                            <i class="fa fa-heart-o"></i>
                                            <span>喜欢和赞</span>
                                        </nuxt-link>
                                    </li>
                                    <li>
                                        <nuxt-link to="/notifications/follows">
                                            <i class="fa fa-user-o"></i>
                                            <span>关注</span>
                                        </nuxt-link>
                                    </li>
                                </ul>
                            </div>
                        </li>
                        <li class="search ">
                            <form action=""method="post">
                                <input type="text" placeholder="搜索" @focus="bgShow = true" @blur="bgShow=false">
                                <nuxt-link to="/search" class="search-btn" :class="{active:bgShow}">
                                    <i class="fa fa-search"></i>
                                </nuxt-link>
                            </form>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                userShow:false,
                infoShow:false,
                bgShow:false,
                showAvatar:true,
            }
        },
        name:'myHeader',//给组件命名
        methods:{
            signOut:function () {
                if(this.$route.path == '/'){
                    this.showAvatar = false;
                }
            }
        }

    }
</script>
<!--当前样式只作用于当前页面-->
<style scoped>
    nav{
        height: 56px;
        width: 100%;
    }
    .navbar {
        padding: 0;
        border-bottom:1px solid #f0f0f0;
        margin-bottom: 20px;
        background-color: #fff;

    }
    .navbar-fixed-top{
        position :fixed;
        top: 0;
        left: 0;
        z-index:9999;
    }
    nav>.width-limit{
        /*最小宽度是768，内容过多超出768时，宽度由内容决定*/
        min-width: 768px;
        width: 1440px;
        margin: 0 auto;
    }
    nav>.width-limit>.nav-logo{
        float: left;
        height:56px;
        padding: 0;
        /*display: block;*/
    }
    nav>.width-limit>.nav-logo img{
        height: 100%;
        /*width: 50%;*/
    }
    a.write-btn{
        float: right;
        width: 100px;
        height: 40px;
        margin: 7px 15px 0;
        line-height: 24px;
        font-size: 15px!important;
        background-color: #ea6f5a;
        color:#fff!important;
        border-radius: 20px;
    }
    a.write-btn:hover{
        background-color: #ec6149;
    }
    nav a.sign-up{
        float: right;
        width: 80px;
        height: 38px;
        margin: 7px 6px 0 10px;
        line-height: 24px;
        font-size: 15px;
        border: 1px solid #ea6f5a;
        border-radius: 20px;
        color:#ea6f5a!important;
    }
    nav a.sign-in{
        float: right;
        margin: 11px 6px 0 10px;
        line-height: 24px;
        font-size: 15px;
        padding: 6px 12px;
        color: #969696 !important;
        border: 0;
    }
    nav a.sign-in:active{
        box-shadow: none;
    }
    nav a.sign-up:hover{
        background-color:#fef7f5;
    }
    nav .user{
        float: right;
        position: relative;

    }
    nav .user .avatar{
        position: relative;
        width: 40px;
        height:40px;
        display: block;
        margin: 8px 28px 8px 20px;

    }
    nav .user:hover{
        background-color: #f5f5f5;
    }
    nav .user .avatar:after{
        content: "";
        position: absolute;
        top: 18px;
        right: -14px;
        border-left: 5px solid transparent;
        border-right: 5px solid transparent;
        border-top: 6px solid #999

    }
    nav .user .avatar img{
        width: 100%;
        height: 100%;
        border:1px solid #ccc;
        border-radius: 50%;
    }
    nav .user .drop-menu{
        position: absolute;
        left: 0;
        min-width: 160px;
        box-shadow: 0 0 8px rgba(0,0,0,.1);
        font-size: 15px;
        background-color: #fff;
    }
    nav .user .drop-menu ul{
        border: 1px solid #ccc;
        padding: 10px 0;
        margin: 0;
    }
    nav .user .drop-menu ul li a{
        display: block;
        padding:10px 20px;
    }
    nav .user .drop-menu ul li a:hover{
        background-color: #f5f5f5;
    }
    nav .user .drop-menu ul li i{
        margin-right: 5px;
        color:#ea6f5a;
        font-size: 18px;
    }
    nav .nav-list{
        zoom:1;
        margin: 0 -15px;
        padding: 0;
    }
    nav .nav-list:after{
        content: "";
        clear: both;
    }
    nav .nav-list>li{
        float: left;
        margin-right: 5px;
    }
    nav .nav-list>li>a{
        height: 55px;
        display: block;
        padding:15px;
        /*padding-left: 0px;*/
        font-size: 17px;
    }
    nav .nav-list>li>a>i{
        margin-right: 7px;
        font-size: 22px;
        /*margin-top: 5px;*/
        text-align: center;
    }
    nav .nav-list>li.active{
        color:#ea6f5a;
        background-color: white!important;
    }
    /**/
    /*nav  hover事件*/
    nav .nav-list li.hover:hover{
        background-color: #f5f5f5;
    }
    nav .nav-list .info-down{
        position: relative;
    }
    nav .nav-list .info-down .info-menu{
        position: absolute;
        left:0;
        top:54px;
        min-width: 170px;
        padding:5px 0;
        margin: 2px 0 0;
        box-shadow: 0 0 8px rgba(0,0,0,.1);
        font-size: 15px;
        background-color: white;
        z-index: 9999;
        color:#000!important;
    }
    nav .nav-list .info-down .info-menu ul{
        padding: 10px 0;
    }
    nav .nav-list .info-down .info-menu ul li:hover{
        background-color: #f5f5f5;
    }
    nav .nav-list .info-down .info-menu ul li a{
        padding: 10px 20px;
        display: block;
        line-height:40px;
        font-size: 14px!important;
        color: #333333 !important;
/*ul>li>a的固定写法，预先保证li标签已经清除浮动了*/
    }
    nav .nav-list .info-down .info-menu ul li a i{
        color: #ea6f5a !important;
        display: inline-block;
        font-size: 22px!important;
        margin-right: 15px;
    }

    /**********************************************************/
    nav .nav-list .search{
        padding-left:15px;
    }
    nav .nav-list .search form{
        margin-top: 9px;
        position: relative;
    }
    nav .nav-list .search form input{
        border: none;
        width: 240px;
        height: 38px;
        border-radius:20px;
        background-color: #eee;
        padding:0 30px 0 20px;
        font-size: 15px;
        transition: width ease-in .3s;
    }
    nav .nav-list .search form input:focus{
        width:320px;
    }
    nav .nav-list .search form a.search-btn{
        display: block;
        position: absolute;
        right: 10px;
        top: 4px;
        width: 30px;
        height: 30px;
        line-height: 30px;
        text-align: center;
    }
    nav .nav-list .search form a.active{
        background-color: #969696;
        border-radius: 50%;
        color:#fff!important;

    }
    nav .nav-list .search form a.search-btn i{
        font-size: 18px;
        position: relative;
        bottom:2px;
    }
    @media(max-width:768px){
        nav .nav-list{
            display: none;
        }
    }
    @media (max-width:1440px) {
        nav .nav-list>li a i.noshow{
            display: none;
        }
        nav .nav-list .search form input{
            width: 160px;
        }
        nav .nav-list .search form input:focus{
            width: 240px;
        }

    }
    @media(min-width: 768px) and (max-width: 1080px){
        nav .nav-list .search form input{
            width: 150px;
        }
        nav .nav-list .search form input:focus{
            width: 150px;
        }
    }
    @media (max-width:1080px){
        nav .nav-list>li a i.noshow{
            display: block;
        }
        nav .nav-list>li>a>span{
            display: none;
        }
        nav .nav-list .info-down .info-menu{
            width: 170px;
        }
    }
    @media(min-width:1080px){
        nav .nav-list .info-down .info-menu{
        width: 200px!important;
        }
    }
</style>