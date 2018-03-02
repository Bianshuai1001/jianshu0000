<template>
    <div class="user">
        <my-header></my-header>
        <div class="my-container">
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
                                        <nuxt-link to="/">
                                            <p>19</p>关注
                                            <i class="fa fa-angle-right"></i>
                                        </nuxt-link>
                                    </div>
                                </li>
                                <li>
                                    <div class="meta-block">
                                        <nuxt-link to="/">
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
                    </div>
                    <div id="outer-container">
                        <ul class="trigger-menu">
                            <li :class="{active:haveborder3}" @click="Showcomments('pinglun')">
                                <a>
                                    <i class="fa fa-comments"></i>
                                    关注的专题/文集/连载 3
                                </a>
                            </li>
                            <li :class="{active:haveborder2}"@click="Showcomments('xihuanwenzhang')">
                                <a>
                                    喜欢的文章 7
                                </a>
                            </li>
                        </ul>
                    </div>
                    <div class="container-list">
                        <guanzhuzhuti v-if="haveborder3"></guanzhuzhuti>
                        <liketext v-if="haveborder2"></liketext>
                    </div>
                </div>
                <div class="col-4 aside">
                    <userRightAside></userRightAside>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import guanzhuzhuti from '~/components/guanzhuzhuti'
    import liketext from '~/components/liketext'
    import userRightAside from '~/components/userRightAside'

    export default{
        data(){
            return {
                haveborder2:false,
                haveborder3:true,
                showedit:false,
            }
        },
        components:{
            myHeader,
            guanzhuzhuti,
            liketext,
            userRightAside
        },
        methods:{
            Showcomments:function (value) {
                if(value == 'xihuanwenzhang'){
                    this.haveborder2=true;
                    this.haveborder3=false;
                }else if(value == 'pinglun'){
                    this.haveborder3=true;
                    this.haveborder2=false;
                }
            }
        }
    }
</script>
<style>

</style>