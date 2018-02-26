<template>
    <div class="my-container" @click="nomore()">
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
                    <div class="show-content">
                        <p>美食和爱情很像，一个惊动味蕾，一个触动感官。你会记得美味入口的那一瞬间，你也忘不了初次相见的那个人。</p>
                        <p>最初的惊艳感仍在，等之后熟悉了，会渐渐化成恬淡的温情。味蕾想念某样食物，心里牵挂一个人。知道他们一直都在，才会心生安定。</p>
                        <p>食物和爱，是怎么也脱不开关系的。厨房间的事一向琐碎，下厨的动力，无非是爱吧。亲人、爱人、好友，挨着坐的亲密，举杯一饮而快，或只是闲聊碎语，多少故事在此间发生。</p>
                        <p>今天想聊一聊日本女作家向田邦子。在她的散文、小说和书信中，常常提到各式食物，而展开来，说到底，与之相关的，还是人间的种种情感。她爱美食，“我靠写字赚钱已有二十年，但比起拿笔的时间，拿筷子的</p>
                        <p>时间肯定更长。”担当编剧，敏锐观察日常的她，记录下来的这些食物故事，是有温度的，带着她独有的柔情笔触</p>
                    </div>
                    <div class="show-foot">
                        <nuxt-link to="/nb/123" class="notebook">
                            <i class="fa fa-book"></i>
                            <span>我的文集</span>
                        </nuxt-link>
                        <div class="copyright">
                            &copy;版权归作者所有
                        </div>
                    </div>
                    <div class="follow-detail">
                        <div class="info">
                            <nuxt-link to="/" class="avatar">
                                <img src="../../assets/img/tag-1.jpg" alt="">
                            </nuxt-link>
                            <a href="javascript:void(0)" class="btn btn-success follow":class="atteObj" @click="atteShow()"@mouseenter="yiru2()"@mouseleave="yichu2()">
                                <i class="fa" :class="iconObj" ref="icon2"></i>
                                <span ref="guanzhuText2">关注</span>
                            </a>
                            <nuxt-link to="/u/123" class="title">
                                测试用户
                            </nuxt-link>
                            <i class="fa fa-mars"></i>
                            <p>写了105763字，被1208人关注，获得了2760个喜欢</p>
                        </div>
                        <div class="signature">
                            为城市里的不安和孤寂发声
                        </div>
                    </div>
                    <div class="meta-bottom">
                        <div class="like">
                            <div class="btn like-group":class="changeObj">
                               <div class="btn-like">
                                   <a href="javascript:void(0)"@click="changeColor()">
                                       <i class="fa" :class="heartObj"></i>
                                       <span>喜欢</span>
                                   </a>
                               </div>
                               <div class="modal-wrap">
                                    <a  @click="showModal">{{likecount}}</a>
                                   <b-modal ref="myModalRef" hide-footer title="喜欢的用户" class="like-modal">
                                       <div class="d-block text-center">

                                       </div>
                                   </b-modal>
                                </div>
                            </div>
                        </div>
                        <div class="share-group">
                            <a href="javascript:void(0)" v-b-tooltip.hover title="分享到微信">
                                <i class="fa fa-weixin weixin"></i>
                            </a>
                            <a href="javascript:void(0)" v-b-tooltip.hover title="分享到微博">
                                <i class="fa fa-weibo weibo"></i>
                            </a>
                            <a href="javascript:void(0)" v-b-tooltip.hover title="下载长微博图片">
                                <i class="fa fa-photo photo"></i>
                            </a>
                            <a href="javascript:void(0)" class="more-share"@click.stop="showmore()">
                                <ul class="share-list" ref="moreul">
                                    <li>
                                        <i class="fa fa-star qq"></i>
                                        <span>分享到QQ空间</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-twitter twitter"></i>
                                        <span>分享到Twitter</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-facebook-official facebook"></i>
                                        <span>分享到Facebook</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-google-plus google"></i>
                                        <span>分享到谷歌</span>
                                    </li>
                                    <li>
                                        <i class="fa fa-github github"></i>
                                        <span>分享到Github</span>
                                    </li>
                                    <img src="../../assets/img/sanjiao.png" alt="">
                                </ul>
                                更多分享
                            </a>
                        </div>
                    </div>
                </div>
                <!--回复组件-->
                <my-comment></my-comment>

            </div>
            <!--悬浮的操作框-->
            <div class="side-bar"></div>
            <!--对应的推荐阅读-->
            <div class="note-bottom"></div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import myComment from '~/components/myComment'

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
                },
                changeObj:{
                    'change-nolike':true,
                    'change-like':false,
                },
                like:false,
                heartObj:{
                    'fa-heart-o':true,
                    'fa-heart':false
                },
                likecount:66,
            }
        },
        components:{
            myHeader,
            myComment,
        },
        methods:{
            atteShow:function () {
              let text = this.$refs.guanzhuText.innerHTML;
              //这里预留关注的ajax的操作
              //以下操作都是在发送请求成功之后
              this.atteObj['no-atte'] = !  this.atteObj['no-atte'];
              this.atteObj['atte'] = ! this.atteObj['atte'];
              this.iconObj['fa-plus-square-o'] = ! this.iconObj['fa-plus-square-o'];
              this.iconObj['fa-check'] = ! this.iconObj['fa-check'];
              this.$refs.guanzhuText.innerHTML = text == '关注' ? '已关注' : '关注';
              this.$refs.guanzhuText2.innerHTML = text == '关注' ? '已关注' : '关注';
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
            },
//          为了使两个关注按钮的移入移出事件互不影响，设置两个函数
            yiru2:function () {
                let text = this.$refs.guanzhuText2.innerHTML;
                if(text == '已关注'){
                    this.$refs.icon2.className = 'fa fa-close';
                    this.$refs.guanzhuText2.innerHTML = '取消关注';
                }
            },
            yichu2:function () {
                let text = this.$refs.guanzhuText2.innerHTML;
                if(text == '取消关注'){
                    this.$refs.icon2.className = 'fa fa-check';
                    this.$refs.guanzhuText2.innerHTML = '已关注';
                }
            },
            changeColor:function () {
                this.changeObj['change-nolike'] = ! this.changeObj['change-nolike'];
                this.changeObj['change-like'] = ! this.changeObj['change-like'];
                this.heartObj['fa-heart-o'] = ! this.heartObj['fa-heart-o'];
                this.heartObj['fa-heart'] = ! this.heartObj['fa-heart']
//                let count =  this.$refs.likecount.innerHTML
//                let count2 = Number(count)
//                console.log(typeof(count2));
                this.like = ! this.like;
                if(this.like){
                    this.likecount =  this.likecount + 1;
//                    预留发送ajax请求的地方
                }else{
                    this.likecount =  this.likecount - 1;
                }

            },
            showmore:function () {
                this.$refs.moreul.style.display = 'block';
            },
            nomore:function () {
                this.$refs.moreul.style.display = 'none';

            },
            showModal () {
                this.$refs.myModalRef.show()
            },
            hideModal () {
                this.$refs.myModalRef.hide()
            }
        }
    }
</script>