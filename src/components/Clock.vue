<template>
    <div class="js-clock">
     {{hours}}:{{minutes}}:{{seconds}}:{{hourSystem}}
    </div>
</template>
<script>
export default {
     data(){
       return{
         hours:'__',
         minutes:'__',
         seconds:'__',
         hourSystem:'__'
       }
     },
    methods: {
      getZero(n) {
        return (parseInt(n,10) >= 10 ? '' : '0') + n;
      },
      
      timeGetter(){
         const time = new Date()
         this.hours = this.getZero(time.getHours());
         this.minutes = this.getZero(time.getMinutes());
         this.seconds= this.getZero(time.getSeconds());                    
      }
    },
    watch: {
      hours(now){
        now >12 ?  (this.hourSystem ="PM") : (this.hourSystem="AM");        
      }
    },
    mounted() {
      this.clockContainer = setInterval(this.timeGetter,1000);
    }
    
}
</script>

<style scoped>

</style>