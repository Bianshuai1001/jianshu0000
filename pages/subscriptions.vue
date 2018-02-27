<template>
    <div>
        <my-header></my-header>
        <div class="my-container subscriptions">
            <div class="row">
                <div class="aside col-4">
                    <subscriptionLeft></subscriptionLeft>
                </div>
                <div class="main col-8">
                    <noteList></noteList>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import myHeader from '~/components/myHeader'
    import subscriptionLeft from '~/components/subscriptionLeft'
    import noteList from '~/components/notelist'
    export default{
        components:{
            myHeader,
            subscriptionLeft,
            noteList
        },
    }
</script>
<style>
    .subscriptions .row{
        padding-top: 30px;
    }

</style>