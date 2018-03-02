<template>
    <div class="my-container nb uaer">
        <my-header></my-header>
        <div class="row">
            <div class="main col-8">
                <div class="main-top">
                    <nuxt-link to="/" class="avatar-collection">
                        <img src="../../static/avatar-notebook-default.png" alt="">
                    </nuxt-link>
                    <div class="title">
                        <nuxt-link to="/">随笔</nuxt-link>
                    </div>
                    <div class="info">
                        1篇文章&nbsp;&nbsp;·&nbsp;&nbsp;2000字&nbsp;&nbsp;·&nbsp;&nbsp;560人关注
                    </div>
                </div>
                <div id="outer-container">
                    <ul class="trigger-menu">
                        <li :class="{active:haveborder1}" @click="name='wenzhang';haveborder1=true;haveborder2=false;haveborder3=false;haveborder4=false;" @mouseover="Tolong('wenzhang')" @mouseleave="Toshort('wenzhang')">
                            <a>
                                <i class="fa fa-file-text"></i>
                                最新发布
                            </a>
                            <div class="hoverborder" id="wenzhang"></div>
                        </li>
                        <li :class="{active:haveborder2}"@click="name='dongtai';haveborder2=true;haveborder1=false;haveborder3=false;haveborder4=false;" @mouseover="Tolong('dongtai')" @mouseleave="Toshort('dongtai')">
                            <a>
                                <i class="fa fa-bell"></i>
                                最新评论
                            </a>
                            <div class="hoverborder" id="dongtai"></div>
                        </li>
                        <li :class="{active:haveborder3}" @click="name='pinglun';haveborder3=true;haveborder2=false;haveborder1=false;haveborder4=false;" @mouseover="Tolong('pinglun')" @mouseleave="Toshort('pinglun')">
                            <a>
                                <i class="fa fa-comments"></i>
                                目录
                            </a>
                            <div class="hoverborder" id="pinglun"></div>
                        </li>
                    </ul>
                </div>
                <div id="list-container">
                    <!--动态组件-->
                    <component :is="currentTab" keep-alive></component>
                </div>
            </div>
            <div class="aside col-4">
                <div class="share">
                    <span>分享到</span>
                    <a class="option" href="#">
                        <i class="fa fa-weibo"></i>
                    </a>
                    <a class="option">
                        <i class="fa fa-weixin"></i>
                    </a>
                </div>
                <div class="wenji">
                    <p class="title">文集作者</p>
                    <ul class="list collection-editor">
                        <li style="vertical-align: middle;">
                            <nuxt-link to="/u/123" class="avatar" style="margin-right: 5px;display: block;margin-top: 5px">
                                <img src="../../static/touxiang.jpg">
                            </nuxt-link>
                            <nuxt-link to="/u/123" class="name"style="display: block;padding-left:40px;">
                                且诺余生
                            </nuxt-link>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import NewArticle from '~/components/nb/NewArticle'
    import NewComment from '~/components/nb/NewComment'
    import Contents from '~/components/nb/Contents'
    export default{
        data(){
            return{
                haveborder1:true,
                haveborder2:false,
                haveborder3:false,
                haveborder4:false,
                currentTab:'NewArticle'
            }
        },
        components:{
            myHeader,
            NewArticle,
            NewComment,
            Contents
        },
        methods:{
            Tolong:function (value) {
                var wenzhang = document.getElementById('wenzhang');
                var dongtai = document.getElementById('dongtai');
                var pinglun = document.getElementById('pinglun');
                var remen = document.getElementById('remen');
                if(value == 'wenzhang'){
                    wenzhang.style.width = '100%';
                    wenzhang.classList.add("changelong");
                    wenzhang.classList.remove("changeshort");
                }else if(value == 'dongtai'){
                    dongtai.style.width = '100%';
                    dongtai.classList.add("changelong");
                    dongtai.classList.remove("changeshort");
                }else if( value == 'pinglun'){
                    pinglun.style.width = '100%';
                    pinglun.classList.add("changelong");
                    pinglun.classList.remove("changeshort");
                }else if(value == 'remen'){
                    remen.style.width = '100%';
                    remen.classList.add("changelong");
                    remen.classList.remove("changeshort");
                }
            },
            Toshort:function (value) {
                var wenzhang = document.getElementById('wenzhang');
                var dongtai = document.getElementById('dongtai');
                var pinglun = document.getElementById('pinglun');
                var remen = document.getElementById('remen');
                if(value == 'wenzhang'){
                    wenzhang.style.width = '0';
                    wenzhang.classList.add("changeshort");
                    wenzhang.classList.remove("changelong");
                }else if(value == 'dongtai'){
                    dongtai.style.width = '0';
                    dongtai.classList.add("changeshort");
                    dongtai.classList.remove("changelong");
                }else if( value == 'pinglun'){
                    pinglun.style.width = '0';
                    pinglun.classList.add("changeshort");
                    pinglun.classList.remove("changelong");
                }else if(value == 'remen'){
                    remen.style.width = '0';
                    remen.classList.add("changeshort");
                    remen.classList.remove("changelong");
                }
            },
        }
    }
</script>
<style>
.nb .row{
    padding-top: 30px;
}
.nb .row .main .main-top{
    margin-bottom: 35px;
}
.nb .row .main .main-top .avatar-collection{
    float: left;
    width: 80px;
    height: 80px;
}
.nb .row .main .main-top .avatar-collection img{
    width: 100%;
    height: 100%;
    border-radius: 4px;
}
.nb .row .main .main-top .title{
   padding: 10px 0 0 100px;
    color:#333;
}
.nb .row .main .main-top .title a{
    font-size: 21px;
    font-weight: 700;
    vertical-align: middle;
    display: inline;
}
.nb .row .main .main-top .info{
    margin-top: 10px;
    padding-left: 100px;
    font-size: 14px;
    color:#969696;
}


.nb .row .main  #outer-container .trigger-menu{
    margin-bottom: 20px!important;
    border-bottom: 1px solid #f0f0f0;
}
.nb .row .main  #outer-container .trigger-menu li{
    display: inline-block;
    padding-top: 8px!important;
    padding-bottom: 0px !important;
    margin-bottom: -1px;
    position: relative;
    cursor: pointer;
}
/*hoverborder  动画样式*/
.nb .row .main #outer-container .trigger-menu li:hover a{
    color: #333333 !important;
}
.nb .row .main #outer-container .trigger-menu li.active{
    border-bottom: 2px solid #646464;
}
.nb .row .main #outer-container .trigger-menu li a{
    padding: 13px 20px 0;
    font-size: 15px;
    font-weight: 700;
    color: #646464 !important;
    line-height: 25px;
    display: inline-block;
    margin-bottom:8px;
}
.nb .row .main #outer-container .trigger-menu li a::after:hover{
    animation:change 0.5s ease-in infinite;
}
@keyframes tolong {
    0%{
        width: 0;
        height: 2px;
    }
    100%{
        width: 100%;
        height: 2px;
    }
}
@keyframes toshort {
    0%{
        width: 100%;
        height: 2px;
    }
    100%{
        width:0;
        height: 2px;
    }
}
.changelong{
    animation:tolong 0.2s;
}
.changeshort{
    animation:toshort 0.2s;
}
.nb .row .main #outer-container .trigger-menu li .hoverborder{
    background-color: #646464;
    height: 2px;
    position: relative;
    top: 2px;
    margin: 0 auto;
    width: 0;
}

.nb .aside .wenji>.title{
    display: block!important;
}
.nb .aside .share {
    margin-bottom: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid #f0f0f0;
    line-height: 30px;
}
.nb .aside .share span {
    font-size: 14px;
    vertical-align: middle;
}
.nb .aside .share .option {
    margin-left: 10px;
    color: #333;
}
.nb .aside .share i {
    font-size: 22px;
    vertical-align: middle;
}
</style>