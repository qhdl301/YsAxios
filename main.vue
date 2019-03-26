<template>
    <div>{{}}</div>
</template>
<script>
  import axios from 'axios'
     export default {
       data() {        
        return {
          locYn : ''
        } 
      },
      mounted() {
        
      },

      methods:{
        getMiseData(){
          var _this = this;
          var miseAddrKey = 'HhZIHZVKtYvTeXRVfIYhfVLZPGlvVjWEhKHKk4X%2F%2Fol0SCriRxuZMdE3TwDiuJAS7IUVqgb4GSz7qN%2BIOtjPCg%3D%3D';
          var reqUrl = "http://openapi.airkorea.or.kr/openapi/services/rest/MsrstnInfoInqireSvc/getNearbyMsrstnList?tmX="+_this.$data.latitude+"&tmY="+_this.$data.longitude+"&pageNo=1&numOfRows=10&ServiceKey="+miseAddrKey;
            _this.axios.get(reqUrl).then(function(result){ // _this를 안붙이면 ->  blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
                                                           // 붙이면 콘솔에 -> Cannot read property 'get' of undefined
            console.log(result);
          })
        }
  }
</script> 
