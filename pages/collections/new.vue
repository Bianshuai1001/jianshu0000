<template>
    <div class="my-container new">
        <my-header></my-header>
        <div class="row">
            <div class="main col-9">
                <h3>新建专题</h3>
                <table>
                    <tbody class="base ">
                        <tr>
                            <td>
                                <div class="avatar-collection">
                                    <img src="../../static/newzhuanti.png" alt="">
                                </div>
                            </td>
                            <td class="toup">
                                <a class="btn btn-hollow"href="javascript:void(0)">上传专题封面</a>
                            </td>
                        </tr>
                        <tr>
                           <td class="setting-title">名称</td>
                            <td>
                                <input type="text" name="nick-name" placeholder="填写名称，不超过50字">
                            </td>
                        </tr>
                        <tr>
                            <td class="setting-title float-left">描述</td>
                            <td>
                                <textarea name="miaoshu" placeholder="填写描述"></textarea>
                            </td>
                        </tr>
                        <tr>
                            <td class="setting-title">其他管理员</td>
                            <td>
                                <input type="text" name="nick-name" placeholder="输入用户名">
                            </td>
                        </tr>
                        <tr>
                            <td class="setting-title">是否允许投稿</td>
                            <td>
                                <div class="col-6 radio">
                                    <input type="radio" name="yunxu" checked @click="noallow = false"><span >允许</span>
                                </div>
                                <div class="radio">
                                    <input type="radio" name="yunxu" @click="noallow = true"><span>不允许</span>
                                </div>
                            </td>
                        </tr>
                        <tr :class="{noallow:noallow}">
                            <td class="setting-title">投稿是否需要审核</td>
                            <td>
                                <div class="col-6 radio">
                                    <input type="radio" name="xuyao" checked><span>需要</span>
                                </div>
                                <div class="radio">
                                    <input type="radio" name="xuyao"><span>不需要</span>
                                </div>
                            </td>
                        </tr>
                    </tbody>
                </table>
                <div class="btn btn-success follow create">创建专题</div>
            </div>
        </div>
    </div>
</template>
<style>
    @media(max-width:748px){
        .new .row .main{
            margin: 0 9px!important;
            /*padding:0 15px!important;*/
            width: 90% !important;
        }
        .new .row{
            /*margin: 0 9px!important;*/
            padding:0 15px 0 0!important;
        }
        .new .row .main tr td{
            display: block;
        }
        .new .row .main tr td:nth-child(1){
            width: 100%;
        }
    }
.new .row .main{
    margin-bottom: 60px;
    width: 75%;
    margin-left: 12.5%;
    padding:0 15px;
}
.new .row .main h3{
    margin: 10px 0 20px;
    font-size: 21px;
    font-weight: 700;
    color: #333333 !important;
}
.new .row .main table{
    width: 100%;
}
.new .row .main table tr td:nth-child(1){
    width: 150px;
    text-align: left;
}
.new .row .main td{
    padding: 16px 0;
    font-size: 15px;
}
.new .row .main .avatar-collection{
    width: 100px;
    height: 100px;
}
.new .row .main .avatar-collection img{
    width: 100%;
    height: 100%;
    border: 1px solid #ddd;
    border-radius: 10%;
}
.new .row .main .base .toup a{
    display: inline-block;
    font-size: 14px;
    border: 1px solid rgba(59,194,29,.7);
    color: #42c02e!important;
    padding: 4px 12px;
    font-weight: 400;
    line-height: normal;
    border-radius: 40px;
    background: none;
}
.new .row .main .setting-title{
    font-size: 15px;
    color:#969696;
}
.new .main input {
    padding: 10px 15px;
    font-size: 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color: #f8f8f8;
}
input[name=nick-name]{
    width: 100%;
}
textarea[name=miaoshu]{
    width: 100%;
    height: 100px;
    margin-bottom: 10px;
    padding:10px 15px;
    border: 1px solid #c8c8c8;
    border-radius: 4px;
    background-color: #f8f8f8;
    resize: none;
    outline-style: none;
}
input[type=radio]{
    margin: 4px 0 0;
}
.new .row .main span{
    margin: 0 5px 0 10px;
    font-size: 15px;
    color: #333;
    vertical-align: middle;
    /*margin-right: 100px;*/
}
.new .row .main .radio{
    display: inline-block;
    padding-left: 0!important;
}
.new .row .main .create{
    font-size: 15px;
    margin: 20px 0 50px;
    padding: 8px 22px;
    border-radius: 20px;
    background-color: #42c02e;
    color: #ffffff !important;

}
.new .row .main .noallow{
        opacity: 0.2;
        cursor: not-allowed;
}
.new .row .main .noallow input{
    cursor: not-allowed;
    }
</style>
<script>
    import myHeader from '~/components/myHeader'
    export default{
        data(){
          return {
              noallow:false
          }
        },
        components:{
            myHeader
        }
    }
</script>