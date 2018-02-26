<template>
    <div>
        <my-header></my-header>
        <div class="index my-container">
            <div class="row">
                <div class="col-8 main">
                    <div v-swiper:mySwiper="swiperOption" class="banner">
                        <div class="swiper-wrapper">
                            <div class="swiper-slide" v-for="banner in banners">
                                <img :src="banner">
                            </div>
                        </div>
                        <div class="swiper-pagination swiper-pagination-white" slot="pagination"></div>
                        <div class="swiper-button-prev swiper-button-white" slot="button-prev"></div>
                        <div class="swiper-button-next swiper-button-white" slot="button-next"></div>
                    </div>
                    <!--推荐专题-->
                    <div class="recommend-collection">
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-1.jpg" alt="">
                            <span>文学</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-2.jpg" alt="">
                            <span>摄影</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-3.jpg" alt="">
                            <span>故事</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-4.jpg" alt="">
                            <span>读书</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-5.jpg" alt="">
                            <span>手绘</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-6.jpg" alt="">
                            <span>旅行·在路上</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-6.jpg" alt="">
                            <span>旅行·在路上</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123">
                            <img src="../assets/img/tag-6.jpg" alt="">
                            <span>旅行·在路上</span>
                        </nuxt-link>
                        <nuxt-link to="/collection/123" class="more-hot-collection">
                            更多热门专题
                            <i class="fa fa-angle-right"></i>
                        </nuxt-link>
                    </div>
                    <div class="split-line"></div>
                    <!--文章列表-->
                    <div id="list-container">
                        <ul class="note-list">
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-3.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-1.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        如何把书中知识转化为能力？这是我见过最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li >
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-2.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        你都不养我小，我还有必要管你老吗？
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-1.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-3.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        这是我的大学舍友|下铺的“箱子”兄弟
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-4.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-4.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        ［公路］绝对光年 （24）
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-5.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-5.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        儿子读书太快让我有些抓狂
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-6.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-6.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        曾国藩啊，他就是一个笨蛋
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-1.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-1.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        这是我的大学舍友|下铺的“箱子”兄弟
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-2.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-3.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        ［公路］绝对光年 （24）
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li class="have-img">
                                <nuxt-link class="wrap-img" to="/p/123">
                                    <img src="../assets/img/img-3.jpg" alt="">
                                </nuxt-link>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-5.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        如何把书中知识转化为能力？这是我见过最好的回答
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                            <li>
                                <div class="content">
                                    <div class="author">
                                        <nuxt-link to="/u/123" class="avatar">
                                            <img src="../assets/img/tag-1.jpg" alt="">
                                        </nuxt-link>
                                        <div class="info">
                                            <nuxt-link to="/u/123" class="nickname">
                                                测试用户
                                            </nuxt-link>
                                            <span class="time">8小时前</span>
                                        </div>
                                    </div>
                                    <nuxt-link to="/p/123" class="title">
                                        你都不养我小，我还有必要管你老吗？
                                    </nuxt-link>
                                    <p class="abstract">
                                        Ⅰ 寂静的夜晚，月光透过窗户悄悄地映在了杰里的身上，
                                        此刻，他正在床上不停地抖动，头也不停地晃动。 “
                                        滚开！” 他惊得从床上弹了起来，他惶恐地环顾了下四周后
                                        ，重重地松了口气，然...
                                    </p>
                                    <div class="meta">
                                        <nuxt-link to="/collection/123" class="collection-tag">
                                            短篇小说
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-eye"></i>
                                            579
                                        </nuxt-link>
                                        <nuxt-link to="/p/123" class="tag">
                                            <i class="fa fa-comment"></i>
                                            200
                                        </nuxt-link>
                                        <span >
                                            <i class="fa fa-heart"></i>
                                            546
                                        </span>
                                    </div>
                                </div>
                            </li>
                        </ul>
                    </div>
                    <!--阅读更多-->
                    <nuxt-link to="/" class="load-more">
                         阅读更多
                    </nuxt-link>
                    <footer >
                        <ul class="footer-list">
                                    <li><nuxt-link to="/">关于项目</nuxt-link></li>
                                    <li><nuxt-link to="/">邮箱:1548620765@qq.com</nuxt-link></li>
                                    <li><nuxt-link to="/">作者：且诺余生</nuxt-link></li>
                                    <li><nuxt-link to="/">精诚所至，金石为开</nuxt-link></li>
                                </ul>
                    </footer>
                </div>
                <div class="col-4 aside">
                    <div class="board">
                        <nuxt-link to="/">
                            <img src="../assets/img/banner-1.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/banner-2.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/banner-3.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/banner-4.png" alt="">
                        </nuxt-link>
                        <nuxt-link to="/">
                            <img src="../assets/img/banner-5.png" alt="">
                        </nuxt-link>
                    </div>
                    <nuxt-link to="/" class="download">
                        <img src="../assets/img/weixin.png" alt="" class="big">
                        <img src="../assets/img/weixin.png" alt="" class="small">
                        <img src="../assets/img/sanjiao.png" alt="" class="sanjiao">
                        <span>联&nbsp;系&nbsp;作&nbsp;者</span>
                    </nuxt-link>
                    <div class="recommend-author">
                        <div class="title">
                            <span>推荐作者</span>
                            <a href="javascript:void(0)" class="page-change" @click="rotate">
                                <i class="fa fa-refresh" ref="refresh"></i>
                                换一批
                            </a>
                        </div>
                        <ul class="list">
                            <li>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="../assets/img/touxiang.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    关注
                                    <i class="fa fa-plus-square-o"></i>
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    且诺余生
                                </nuxt-link>
                                <p>
                                    写了152.9k字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="../assets/img/tag-2.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    关注
                                    <i class="fa fa-plus-square-o"></i>
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    简书出版
                                </nuxt-link>
                                <p>
                                    写了152.9k字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="../assets/img/tag-3.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    关注
                                    <i class="fa fa-plus-square-o"></i>
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    雪花如糖
                                </nuxt-link>
                                <p>
                                    写了152.9k字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="../assets/img/tag-4.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    关注
                                    <i class="fa fa-plus-square-o"></i>
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    名贵的考拉熊
                                </nuxt-link>
                                <p>
                                    写了152.9k字·7.2k喜欢
                                </p>
                            </li>
                            <li>
                                <nuxt-link class="avatar" to="/u/123">
                                    <img src="../assets/img/tag-5.jpg" alt="">
                                </nuxt-link>
                                <nuxt-link class="follow" to="/u/123">
                                    关注
                                    <i class="fa fa-plus-square-o"></i>
                                </nuxt-link>
                                <nuxt-link to="/u/123" class="name">
                                    POPO熊
                                </nuxt-link>
                                <p>
                                    写了152.9k字·7.2k喜欢
                                </p>
                            </li>
                        </ul>
                        <nuxt-link to="/" class="find-more">
                            查看更多
                            <i class="fa fa-angle-right"></i>
                        </nuxt-link>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
            return {
                banners:[
                    '/lunbo-1.jpg',
                    '/lunbo-2.jpg',
                    '/lunbo-3.jpg',
                    '/lunbo-4.jpg',
                ],
                swiperOption: {
                    autoplay:{
                      delay:3000,//切换时间
                      stopOnLastSlide:false,//是否停留在最后一张
                      disableOnInteraction:false,//是否禁止轮播
                    },
                    loop: true,
                    slidesPerView: 'auto',
                    centeredSlides: true,
                    spaceBetween: 30,
                    pagination: {
                        el: '.swiper-pagination',
                        clickable:true,
                    },
                    navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev'
                    },
                },
                deg:0,
            }
        },
        components:{
            myHeader
        },
        methods:{
            rotate:function () {
                this.deg = this.deg + 360
                console.log(this.$refs.refresh)
                this.$refs.refresh.style.transform = `rotate(${this.deg}deg)`;
                console.log(this.deg);
            }
        }
    }
</script>
<style>
    .swiper-button-next,.swiper-button-prev{
        background-color:rgba(0,0,0,0.4);
    }


</style>