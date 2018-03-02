<template>
    <div>
        <ul class="note-list">
            <li>
                <div class="content">
                    <div class="author">
                        <nuxt-link to="/u/123" class="avatar">
                            <img src="../../static/touxiang.jpg">
                        </nuxt-link>
                        <div class="info">
                            <nuxt-link to="/u/123" class="nickname">简宝玉</nuxt-link>
                            <span class="time">02.10 17:20</span>
                        </div>
                    </div>
                    <nuxt-link class="title" to="/p/123">
                        提现没有到账怎么办?
                    </nuxt-link>
                    <p class="abstract">

                        提现多久可以到账 简书的提现，一般3个“工作日”会到账，到账后，你可以在支付宝，“我的-账单”里确认，转账方为”上海佰集信息科技有限公司“。 如何在简书内，查看提现是否到账 ...
                    </p>
                    <div class="meta">
                        <nuxt-link class="tag" to="/p/123">
                            <i class="fa fa-eye"></i>
                            100
                        </nuxt-link>
                        <nuxt-link class="tag" to="/p/123">
                            <i class="fa fa-comment"></i>
                            200
                        </nuxt-link>
                        <span>
                            <i class="fa fa-heart"></i>
                            15
                        </span>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        name:'Contents'
    }
</script>
<style>
    .note-list .meta span {
        margin-right: 10px;
        color: #b4b4b4;
    }
    .note-list .meta a {
        margin-right: 10px;
        color: #b4b4b4;
    }
    .note-list .comment {
        font-size: 15px;
        line-height: 1.7;
    }
    .note-list blockquote {
        margin-bottom: 0;
        color: #969696;
        border-left: 3px solid #d9d9d9;
        padding: 10px 20px;
        margin: 0 0 20px;
        font-size: 17.5px;
    }
    .note-list blockquote .title {
        display:block;
        margin: 0 0 4px;
        font-size: 15px;
        color:#333!important;
    }
    .note-list blockquote .abstract {
        margin: 0 0 4px;
    }
    .note-list .origin-author {
        display: inline;
        margin-bottom: 5px;
        font-size: 12px;
        color: #969696!important;
    }
    .note-list .origin-author a {
        margin-right: 5px;
        color: #3194d0!important;
    }

    .note-list .origin-author a {
        color: #3194d0!important;
    }
    .note-list .follow-detail {
        padding: 20px;
        background-color: hsla(0,0%,71%,.1);
        border: 1px solid #e1e1e1;
        border-radius: 4px;
        font-size: 12px;
    }
    .note-list .follow-detail .avatar, .note-list .follow-detail .avatar-collection {
        float: left;
        margin-right: 10px;
        width: 48px;
        height: 48px;
    }
    .note-list .follow-detail .btn {
        float: right;
        margin-top: 4px;
        padding: 8px 0;
        width: 100px;
    }
    .note-list .follow-detail .follow {
        border-radius: 40px;
        color: #fff!important;
        background-color: #42c02e;
    }
    .note-list .follow-detail .follow span {
        margin-left:5px;
    }
    .note-list .follow-detail .info {
        display:block;
    }
    .note-list .follow-detail .info .title {
        margin: 0;
        font-size: 17px;
        font-weight: 400;
    }
    .note-list .follow-detail .info p {
        margin-bottom: 0;
        color: #969696;
    }
    .note-list .follow-detail .signature {
        margin-top: 20px;
        padding-top: 20px;
        border-top: 1px solid #e1e1e1;
        color: #969696;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
    }
    .avatar-collection img {
        width: 100%;
        height: 100%;
        border: 1px solid #ddd;
        border-radius: 10%;
    }
    .note-list .follow-detail .creater, .note-list .follow-detail .creater:hover {
        color: #3194d0;
    }
</style>