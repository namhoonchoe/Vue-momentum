<template>
<body>
    <img src="../assets/1.jpg" 
         v-if="randNum === 1"
         alt="bgimg1">
    <img src="../assets/2.jpg" 
         v-else-if="randNum === 2"
         alt="bgimg2">
    <img src="../assets/3.jpg" 
         v-else-if="randNum === 3"
         alt="bgimg3">
    <img src="../assets/4.jpg" 
         v-else
         alt="bgimg4">
</body>  
</template>

<script>
export default {
    data(){
        return{
            randNum:''
        }
    },
    methods:{
        genRandom() {
            const imgNum = 4;
            const randNum = Math.floor((Math.random)*imgNum);
            return randNum;
        }
    },
    mounted() {
        this.randNum = this.genRandom()
    }
}
</script>

<style>

</style>