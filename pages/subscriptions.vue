<template>
    <div>
        <my-header></my-header>
        <div class="my-container subscriptions">
            <div class="row">
                <div class="aside">
                    <subscriptionLeft></subscriptionLeft>
                </div>
                <div class="col-8">

                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import subscriptionLeft from '~/components/subscriptionLeft'
    export default{
        components:{
            myHeader,
            subscriptionLeft,
        },
    }
</script>
<style>
    .subscriptions .row{
        padding-top: 30px;
    }

</style>