<template>
    <div class="sign">
        <!--logo-->
        <div class="logo">
            <nuxt-link to="/">
                <img src="../assets/img/logo.png">
            </nuxt-link>
        </div>
        <!--注册表单-->
        <div class="main">
            <div class="title">
                <h4>
                    <nuxt-link to="/sign-in">
                        登录
                    </nuxt-link>
                    <b>·</b>
                    <nuxt-link class="active" to="/sign-up">
                        注册
                    </nuxt-link>
                </h4>
            </div>
            <div class="js-sign-up">
                <form method="post">
                    <div class="input-prepend">
                        <input type="text" name="" value="" placeholder="你的昵称" class="top-radius">
                        <i class="fa fa-user"></i>

                    </div>
                    <div class="input-prepend">
                        <input type="text" name="" value="" placeholder="手机号">
                        <i class="fa fa-phone"></i>
                    </div>
                    <div class="input-prepend ssm">
                        <input type="text" name="" value="" placeholder="手机验证码">
                        <i class="fa fa-shield"></i>
                        <a class="send-ssm btn btn-success">发送验证码</a>
                    </div>
                    <div class="input-prepend">
                        <input type="text" name="" value="" placeholder="设置密码" class="bottom-radius">
                        <i class="fa fa-lock"></i>
                    </div>
                    <input type="button" class="btn btn-success sign-up-btn" value="注册">
                    <p class="sign-up-msg">
                        点击注册即表示您同意并愿意遵守简书<br>
                        用户协议和隐私政策
                    </p>
                </form>
                <div class="more-sign">
                    <p>社交账号登录</p>
                    <ul>
                        <li class="weixin">
                            <a href="#">
                                <i class="fa fa-weixin"></i>
                            </a>
                        </li>
                        <li class="qq">
                            <a href="#">
                                <i class="fa fa-qq" style="color:white!important;"></i>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        layout:'sign',//指明当前页面所使用的默认模板是layouts文件夹下的sign.vue
        head () {
            return {
                title:"注册-简书",
                meta:[
                    {hide:'description',name:'description',content:'注册页面'}
                ]
            }
        }
    }
</script>
<style>
    @media (max-width:768px) {
        .sign .logo {
            display:none;
        }
        .sign #sign-template{
            background:#fff!important;
        }
        .sign .main {
            box-shadow: none;
            margin:0 auto;
        }
    }
    html,body {
    height:100%;
    background-color:#f1f1f1!important;
    }
    .sign {
        height:100%;
        font-size:14px;
        text-align:center;
    }
    .sign .logo {
        position:absolute;
        top:50px;
        left:50px;
    }
    .sign .logo img {
        width:100px;
    }
    .sign .main {
        width:400px;
        margin:50px auto 0;
        padding:50px 50px 30px;
        background-color:#fff;
        border-radius: 4px;
        box-shadow: 0 0 8px rgba(0,0,0,.1);
        display:inline-block;
    }
    .sign .main .title {
        margin:0 auto 50px;
        padding:10px;
        color:#939393;
    }
    .sign .main .title h4 {
        margin:0;
        font-size:18px;
    }
    .sign .main .title h4 a,.main .title h4 b {
        padding:10px;
    }
    .sign .main .title h4 a.active {
        font-weight:700;
        color:#ea6f5a!important;
        border-bottom:2px solid #ea6f5a;
    }
    .sign .main .title h4 a:hover {
        border-bottom:2px solid #ea6f5a;
    }
    .sign .main form {
        margin:0 0 30px;
        color:#969696;
    }
    .sign .main form .input-prepend {
        position:relative;
        width:100%;
    }
    .sign .main form .input-prepend input {
        width:100%;
        height:50px;
        padding:4px 12px 4px 35px;
        border:1px solid #c8c8c8;
        border-bottom:none;
        background-color:rgb(248,248,248)
    }
    .sign .main form input.top-radius {
        border-radius:4px 4px 0 0;
    }
    .sign .main form input.bottom-radius {
        border-radius:0 0 4px 4px;
        border-bottom:1px solid #c8c8c8;
    }
    .sign .main form .input-prepend i {
        position:absolute;
        color:#969696;
        top:15px;
        left:15px;
        font-size:20px;
    }
    .sign .main form .remember {
        float:left;
        margin:25px 0;
    }
    .sign .main form .help {
        float:right;
        margin:25px 0;
    }
    .sign .main form>input {
        width:100%;
        display:block;
        height:45px;
        border-radius: 20px;
    }
    .main .more-sign p {
        position:relative;
        font-size:14px;
        color:#b8b8b8;
        margin-bottom:20px;
    }
    .main .more-sign p:before {
        content:"";
        width:60px;
        border-bottom:1px solid #b8b8b8;
        position:absolute;
        top:10px;
        left:30px;
    }
    .main .more-sign p:after {
        content:"";
        width:60px;
        border-bottom:1px solid #b8b8b8;
        position:absolute;
        top:10px;
        right:30px;
    }
    .sign .main .more-sign ul {
        margin-bottom:20px;
    }
    .sign .main .more-sign ul li {
        display:inline-block;
        border-radius: 50%;
        color:white;
        margin:0 5px;
    }
    .sign .main .more-sign ul li.weibo {
        background:#e05244;
    }
    .sign .main .more-sign ul li.weixin {
        background:#00bb29;
    }
    .sign .main .more-sign ul li.qq {
        background:#498ad5;
    }
    .sign .main .more-sign ul li a {
        width:50px;
        height:50px;
        line-height:50px;
        display:block;
    }
    .sign .main .more-sign ul li.other {
        background:rgb(248,248,248);
        color:#939393;
    }
    .sign .main .more-sign ul li a i {
        font-size:25px;
    }
    .sign .main form input.sign-up-btn {
        margin-top:20px;
    }
    .sign .main form p.sign-up-msg {
        margin:15px 0;
        text-align:center;
        font-size:12px;
        line-height:20px;
        color:#969696;
    }
    .sign .main form .ssm {
        position:relative;
        line-height:36px;
    }
    .sign .main form .input-prepend a.send-ssm {
        position:absolute;
        top:7px;
        right:10px;
        width:100px;
        height:36px;
        display:block;
        font-size:12px;
        border-radius:20px;
        opacity: .8;
        color:#fff!important;
    }
</style>
