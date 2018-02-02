<template>
    <div><div id="comment-list" class="comment-list">
        <!--提交的留言表单-->
        <form action="" class="new-comment">
            <nuxt-link to="/u/123" class="avatar">
                <img src="../assets/img/tag-2.jpg" alt="">
            </nuxt-link>
            <textarea @focus="send=true" placeholder="写下你的评论" v-model="value">

            </textarea>
            <transition name="fade">
                <div v-if="send" class="write-function-block clearfix">
                    <div class="emoji-modal-wrap ">
                        <a href="javascript:void(0)" class="emoji" @click="showEmoji = ! showEmoji">
                            <i class="fa fa-smile-o"></i>
                        </a>
                        <transition name="fade">
                            <div class="emoji-modal arrow-up" v-if="showEmoji">
                               <vue-emoji @select="selectEmoji"></vue-emoji>
                            </div>
                        </transition>
                    </div>
                    <div class="hint">
                        Ctrl+Enter 发表
                    </div>
                    <!--****************************************a标签的事件-->
                    <a href="javascript:void(0)" class="btn btn-send" @click="sendData">发送</a>
                    <a href="javascript:void(0)" class="cancel" @click="send=false">取消</a>
                </div>
            </transition>
        </form>
        <!--留言的列表-->
        <div id="normal-comment-list" class="normal-comment-list">
            <!--留言的排序-->
            <div class="top-title">
                <span>5条评论</span>
                <a href="javascript:void(0)" class="author-only">只看作者</a>
                <div class="pull-right">
                    <a href="javascript:void(0)" class="active">
                        按喜欢排序
                    </a>
                    <a href="javascript:void(0)">
                        按时间正序
                    </a>
                    <a href="javascript:void(0)">
                        按时间倒序
                    </a>
                </div>
            </div>
            <!--留言的正文-->
            <!--下拉加载时的动画-->
            <div class="comment-placeholder" style="display: none;">
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
            <div :id="'comment-'+comment.id" v-for="(comment,index) in comments" class="comment">
                <div class="comment-content">
                    <div class="author">

                            <nuxt-link to="/u/123" class="avatar">
                                <img :src="comment.user.avatar" alt="">
                            </nuxt-link>

                        <div class="info">
                            <nuxt-link to="/u/123" class="name">
                                {{comment.user.nickname}}
                            </nuxt-link>
                            <div class="meta">
                                <span>
                                    {{comment.floor}}楼
                                    {{comment.created_at}}
                                </span>
                            </div>
                        </div>
                    </div>
                    <div class="comment-wrap"></div>
                </div>
                <div class="sub-comment-list"></div>
            </div>
        </div>
    </div>
    </div>
</template>
<script>
    import vueEmoji from '~/components/vueEmoji'
    export default{
        name:'myComment',
        data(){
            return{
                send:false,
                showEmoji:false,
                value:'',
                comments:[
                    {
                        id:19935725,
                        liked:true,
                        floor:2,
                        likes_count:12,
                        note_id:23054702,
                        user_id:6780849,
                        user:{
                            avatar:'/tag-1.jpg',
                            id:6780849,
                            is_author:false,
                            nickname:'月薪2800不知道怎么花',
                            badgue:null,
                        },
                        created_at:"2018-01-28T15:42:26.000+08:00",
                        children_count:3,
                        compiled_content:"祝贺你",
                        children:[
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'nuoyan'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了",

                            },
                            {
                                id:2088366,
                                user_id:2604717,
                                user:{
                                    id:1604717,
                                    nick_name:'nihao'
                                },
                                parent_id:19965726,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了haha",

                            },
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'gushidawang'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"兄弟，你是天才,我就服你",

                            },
                        ]
                    },
                    {
                        id:19996810,
                        liked:true,
                        floor:3,
                        likes_count:10,
                        note_id:23054702,
                        user_id:6780840,
                        user:{
                            avatar:'/tag-1.jpg',
                            id:6780840,
                            is_author:false,
                            nickname:'月薪2800不知道怎么花',
                            badgue:null,
                        },
                        created_at:"2018-01-28T15:59:26.000+08:00",
                        children_count:3,
                        compiled_content:"临睡前又被暖了一把，棒棒哒，看开头还以为是复仇文呢" +
                        "，没想到最后最后给我撒了把狗粮 😁 喜欢",
                        children:[
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'nuoyan'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了",

                            },
                            {
                                id:2088366,
                                user_id:2604717,
                                user:{
                                    id:1604717,
                                    nick_name:'nihao'
                                },
                                parent_id:19965726,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了haha",

                            },
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'gushidawang'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"兄弟，你是天才,我就服你",

                            },
                        ]
                    },
                    {
                        id:20112755,
                        liked:false,
                        floor:4,
                        likes_count:6,
                        note_id:23054702,
                        user_id: 8195200,
                        user:{
                            avatar:'/tag-1.jpg',
                            id: 8195200,
                            is_author:false,
                            nickname:'快乐的海星',
                            badgue:null,
                        },
                        created_at:"2018-01-28T15:42:26.000+08:00",
                        children_count:3,
                        compiled_content:"现实很残酷，但爱情更无价！！结局暖心，好棒！！",
                        children:[
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'nuoyan'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了",

                            },
                            {
                                id:2088366,
                                user_id:2604717,
                                user:{
                                    id:1604717,
                                    nick_name:'nihao'
                                },
                                parent_id:19965726,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了haha",

                            },
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'gushidawang'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"兄弟，你是天才,我就服你",

                            },
                        ]
                    },
                    {
                        id:19935720,
                        liked:true,
                        floor:5,
                        likes_count:2,
                        note_id:23054702,
                        user_id:6780949,
                        user:{
                            avatar:'/tag-1.jpg',
                            id:6780949,
                            is_author:false,
                            nickname:'倾城之恋',
                            badgue:null,
                        },
                        created_at:"2018-01-28T17:42:26.000+08:00",
                        children_count:3,
                        compiled_content:"剧情的反转,只是为了心中的那点期待",
                        children:[
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'nuoyan'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了",

                            },
                            {
                                id:2088366,
                                user_id:2604717,
                                user:{
                                    id:1604717,
                                    nick_name:'nihao'
                                },
                                parent_id:19965726,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"是你飘了haha",

                            },
                            {
                                id:2088369,
                                user_id:2604707,
                                user:{
                                    id:1604707,
                                    nick_name:'gushidawang'
                                },
                                parent_id:19965725,
                                created_at:"2018-01-28T15:49:26.000+08:00",
                                compiled_content:"兄弟，你是天才,我就服你",

                            },
                        ]
                    },
                    {
                        id:19935789,
                        liked:true,
                        floor:6,
                        likes_count:0,
                        note_id:23054702,
                        user_id:6780908,
                        user:{
                            avatar:'/tag-1.jpg',
                            id:6780908,
                            is_author:false,
                            nickname:'倾城之恋123',
                            badgue:null,
                        },
                        created_at:"2018-01-28T18:42:26.000+08:00",
                        children_count:0,
                        compiled_content:"我还以为男的也不要她了。结局好评",
                        children:[],
                    },
                ]
            }
        },
        components:{
            vueEmoji,
        },
        methods:{
            selectEmoji:function (code) {
                this.showEmoji = false;
                this.value += code;
            },
            sendData:function () {
                console.log('发送value的信息给后端');
            },
        }
    }
</script>
<style>
    /*<!--弹框下降动画-->*/
    .fade-enter-active,.fade-leave-active {
        opacity: 1;
        transition: .3s;
        -webkit-transition: .3s
    }
    .fade-enter,.fade-leave-to {
        opacity: 0;
        transform: translate3d(0,-5%,0);
        -webkit-transform: translate3d(0,-5%,0);
        transition: .3s;
        -webkit-transition: .3s
    }
    .note .post .comment-list{
        padding-top: 20px;
    }
    .note .post .comment-list .new-comment{
        position: relative;
        margin-left: 48px;
        margin-bottom: 20px;
    }
    .note .post .comment-list .avatar{
        width: 38px;
        height: 38px;
        display: inline-block;
        margin-right: 5px;
    }
    .note .post .comment-list .new-comment .avatar{
        position: absolute;
        left: -48px;
    }
    .note .post .comment-list .new-comment textarea{
        width: 100%;
        height: 80px;
        padding:10px 15px;
        border:1px solid #ccc;
        border-radius: 4px;
        display: inline-block;
        vertical-align: top;
        outline-style:none ;
        resize: none;
        font-size: 13px;
        background-color: #f8f8f8;
        /*z-index: 4000;*/
    }
    .note .post .comment-list .new-comment .emoji-modal-wrap{
        position: relative;
    }
    .note .post .comment-list .new-comment .emoji{
        float: left;
        margin-top: 14px;
    }
    .note .post .comment-list .new-comment .emoji i{
        font-size: 25px;
        color:#969696;
    }
    .note .post .comment-list .new-comment .emoji i:hover{
        color:#333;
    }
    .note .post .comment-list .new-comment .hint{
        float: left;
        margin: 20px 0 0 20px;
        color:#969696;
        font-size: 13px;
    }
    .note .post .comment-list .new-comment .cancel{
        float: right;
        font-size: 16px;
        margin: 18px 30px 0 0 ;
        color:#969696!important;
    }
    .note .post .comment-list .new-comment .cancel:hover{
        color: #333333 !important;
    }
    .note .post .comment-list .new-comment .btn-send{
        float: right;
        width: 78px;
        padding:8px 18px;
        margin:10px 0;
        font-size: 18px;
        background-color: #42c02e;
        border-radius: 20px;
        color: #ffffff !important;
        text-align: center;
        box-shadow: none;
    }
    .note .post .comment-list .new-comment .btn-send:hover{
        background-color: #3db922;
    }
    .note .post .comment-list .new-comment .emoji-modal-wrap .emoji-modal{
        position: absolute;
        top:50px;
        left: -48px;
        width: 402px;
        height: 208px;
        padding:10px;
        border: 1px solid #d9d9d9;
        border-radius: 4px;
        box-shadow: 0 5px 25px rgba(0,0,0,0.1);
        z-index: 10001;
        background-color: white;
    }
    /*空心三角形书写方法*/
    .arrow-up:after{
        width: 15px;
        height: 15px;
        content: '';
        display: inline-block;
        border-bottom:1px solid #d9d9d9;
        border-right:1px solid #d9d9d9;
        position: absolute;
        left: 48px;
        top: -1px;
        background: #fff;
        transform: translate3d(0,-50%,0) rotate(-135deg);
    }
    .note .post .comment-list .normal-comment-list{
        margin-top: 30px;
    }
    .note .post .comment-list .top-title{
        padding-bottom: 20px;
        border-bottom: 1px solid #f0f0f0;
    }
    .note .post .comment-list .top-title span{
        font-size: 17px;
        font-weight: 700;
    }
    .note .post .comment-list .top-title .author-only{
        font-size: 12px;
        padding:4px 8px;
        border: 1px solid #e1e1e1;
        border-radius: 12px;
        color: #969696 !important;
        margin-left: 10px;

    }
    .note .post .comment-list .top-title .pull-right a{
        margin-left: 10px;
        font-size: 12px;
        color: #969696 !important;
    }
    .note .post .comment-list .top-title .pull-right a.active{
        color: #2f2f2f !important;
    }
    .note .post .comment-list .comment{
        padding:20px 0 30px 0;
        border: 1px solid #f0f0f0;
    }
    .note .post .comment-list .comment .info {
        display: inline-block;
        vertical-align: middle;
    }
    .note .post .comment-list .comment .info .name{
        font-size: 15px;
    }
    .note .post .comment-list .comment .info .meta{
        font-size: 12px;
        coloc:#969696;
    }


</style>