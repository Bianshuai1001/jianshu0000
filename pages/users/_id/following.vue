<template>
    <div class="following user">
        <my-header></my-header>
        <div class="my-container ">
            <div class="row">
                <div class="col-8 main">
                    <div class="main-top">
                        <nuxt-link to="/" class="avatar">
                            <img src="../../../assets/img/touxiang.jpg" alt="">
                        </nuxt-link>
                        <div class="title">
                            <nuxt-link to="/u/123">且诺余生</nuxt-link>
                        </div>
                        <div class="info">
                            <ul>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/users/123/following">
                                            <p>19</p>关注
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/users/123/followers">
                                            <p>3</p>粉丝
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/">
                                            <p>1</p>文章
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/">
                                            <p>1900</p>字数
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/">
                                            <p>99</p>收获喜欢
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                            </ul>
                        </div>
                        <ul class="trigger-menu">
                            <li :class="{active:currentTab == 'like'}">
                                <a href="javascript:void(0)" @click="toggleTab('like')">
                                    关注用户33
                                </a>
                            </li>
                            <li :class="{active:currentTab == 'guanZhuyonghu'}">
                                <a href="javascript:void(0)" @click="toggleTab('guanZhuyonghu')">
                                    粉丝3
                                </a>
                            </li>

                        </ul>
                        <div id="list-container">
                            <!--动态组件-->
                            <component :is="currentTab" keep-alive></component>
                        </div>
                    </div>
                </div>
                <div class="col-4">
                    <user-right-aside></user-right-aside>
                </div>
            </div>
        </div>


    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import like from '~/components/following/like'
    import guanZhuyonghu from '~/components/following/guanzhuyonghu'
    import userRightAside from '~/components/userRightAside'
    export default {
        data () {
            return {
                currentTab:'like'
            }
        },
        methods:{
            toggleTab:function(tab){
                this.currentTab = tab;
            }
        },
        components:{
            myHeader,
            like,
            guanZhuyonghu,
            userRightAside
        }
    }
</script>
<style>
    .trigger-menu {
        margin-bottom: 20px!important;
        border-bottom: 1px solid #f0f0f0;
        font-size: 0;
        list-style: none;
    }
    .trigger-menu li {
        position: relative;
        display: inline-block;
        padding: 8px 0;
        margin-bottom: -1px;
    }
    .trigger-menu a {
        padding: 13px 20px;
        font-size: 15px;
        font-weight: 700;
        color: #969696!important;
        line-height: 25px;
    }
    .trigger-menu i {
        margin-right: 5px;
        font-size: 17px;
    }
    .trigger-menu li.active {
        border-bottom: 2px solid #646464;
    }
    .trigger-menu .active a, .trigger-menu a:hover {
        color: #646464!important;
    }
    .trigger-menu li:after {
        content: "";
        position: absolute;
        left: 50%;
        bottom: -2px;
        width: 100%;
        opacity: 0;
        border-bottom: 2px solid #646464;
        -webkit-transform: translate(-50%) scaleX(0);
        transform: translate(-50%) scaleX(0);
        transition: .2s ease-in-out
    }
    .trigger-menu li:hover:after {
        opacity: 1;
        -webkit-transform: translate(-50%) scaleX(1);
        transform: translate(-50%) scaleX(1);
        transition: .2s ease-in-out
    }
</style>