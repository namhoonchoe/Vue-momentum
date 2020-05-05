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
      timeGetter(){
          const time = new Date()
          this.hours = time.getHours();     
          this.minutes = time.getMinutes();       
          this.seconds = time.getSeconds();    
      }
    },
    watch: {
      hours(now){
        now >12 ? (this.hourSystem ="PM") : (this.hourSystem="AM");
      }
    },
    mounted() {
      this.clockContainer = setInterval(this.timeGetter,1000);
    }
    
              
}
</script>

<style scoped>

</style>