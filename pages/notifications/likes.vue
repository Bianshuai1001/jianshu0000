<template>
    <div class="my-container likes">
        <my-header></my-header>
        <div class="row">
            <div class="col-4 ">
                <LeftMenu></LeftMenu>
            </div>
            <div class="col-8 main">
                <div class="menu">收到的喜欢和赞</div>
                <div class="find-nothing" v-if="likes.length==0">
                    <img src="../../assets/img/find-nothing.png" alt="">
                    <div>这里还没有内容哦</div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import LeftMenu from '~/components/LeftMenu'
    import myHeader from '~/components/myHeader'
    export default {
        data(){
            return{
                likes:[],
            }
        },
        components:{
            LeftMenu,
            myHeader
        }
    }
</script>
<style>
    .likes .row{
        padding:30px 0;
    }
    .likes .row .main .menu{
        margin-bottom:20px;
        font-size: 14px;
        font-weight: 700;
    }
    .find-nothing{
        margin-top: 150px;
        text-align: center;
    }
    .find-nothing img{
        width: 100px;
    }
    .find-nothing div{
        margin-top: 20px;
        font-size: 14px;
        font-weight: 700;
    }

</style>
