<template>
    <div class="my-container">
        <my-header></my-header>
        <div class="note">
            <!--文章区域-->
            <div class="post">
                <!--正文-->
                <div class="article">
                    <h1 class="title">月薪3000,就该去死吗？</h1>
                    <div class="author">
                        <nuxt-link to="/u/123" class="avatar">
                            <img src="~assets/img/tag-1.jpg" alt="">
                        </nuxt-link>
                        <div class="info">
                            <span class="name">测试用户</span>
                            <a href="javascript:void(0)" class="btn-sm follow":class="atteObj" @click="atteShow()"@mouseenter="yiru()"@mouseleave="yichu()">
                                <i class="fa" :class="iconObj" ref="icon"></i>
                                <span ref="guanzhuText">关注</span>
                            </a>
                            <div class="meta">
                                <span>2018.01.23 16:09</span>
                                <span>字数 2222</span>
                                <span>阅读 66</span>
                                <span>评论 6</span>
                                <span>喜欢 55</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!--悬浮的操作框-->
            <div class="side-bar"></div>
        </div>
        <!--对应的推荐阅读-->
        <div class="note-bottom"></div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
            return{
                atteObj:{
                    'no-atte':true,
                    'atte':false,
                },
                iconObj:{
                    'fa-plus-square-o':true,
                    'fa-check':false,
                }
            }
        },
        components:{
            myHeader,
        },
        methods:{
            atteShow:function () {
              this.atteObj['no-atte'] = !  this.atteObj['no-atte'];
              this.atteObj['atte'] = ! this.atteObj['atte'];
              this.iconObj['fa-plus-square-o'] = ! this.iconObj['fa-plus-square-o'];
              this.iconObj['fa-check'] = ! this.iconObj['fa-check'];
              let text = this.$refs.guanzhuText.innerHTML;
              this.$refs.guanzhuText.innerHTML = text == '关注' ? '已关注' : '关注';
            },
            yiru:function () {
                let text = this.$refs.guanzhuText.innerHTML;
                if(text == '已关注'){
                    this.$refs.icon.className = 'fa fa-close';
                    this.$refs.guanzhuText.innerHTML = '取消关注';
                }
            },
            yichu:function () {
                let text = this.$refs.guanzhuText.innerHTML;
                if(text == '取消关注'){
                    this.$refs.icon.className = 'fa fa-check';
                    this.$refs.guanzhuText.innerHTML = '已关注';
                }
            }
        }
    }
</script>