<template>
  <div id="default-template">
    <nuxt/>
  </div>
</template>
<script>
import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
Vue.use(BootstrapVue)
Vue.filter('time',function (value) {
    var date = new Date(value);
    let year = date.getFullYear();
    let month = date.getMonth() + 1;
    let day = date.getDate();
    let hour = date.getHours();
    let minute = date.getMinutes();
    function fillZero(num) {
       return num > 10 ? num :'0'+num
    }
    return fillZero(year)+'.'+ fillZero(month)+'.'+ fillZero(day)+' '+
        fillZero(hour)+':'+ fillZero(minute);
})
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
export default {
    filters:{
        time: function (value) {
            var d = new Date(value);
            var year = d.getFullYear();
            var month = d.getMonth() + 1;
            var day = d.getDate()<10 ? '0' + d.getDate() : '' + d.getDate();
            var hour = d.getHours();
            var minutes = d.getMinutes();
            var seconds = d.getSeconds();
            return  year+ '-' + month + '-' + day + ' ' + hour + ':' + minutes + ':' + seconds;
        }
    }
}
</script>
