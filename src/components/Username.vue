<script>
export default {
    data(){
      return{
         userName:'' 
      };
    },
    mehtods:{
        saveUsername(){

        },
        removeUsername(){

        },
        modifyUsername(){
            
        }
    },
    render(h) {
        if ( this.userName === ''){
            return (
                <div class="greetings">  
                  <input type="text"
                    placeholder="Write your name"/>                     
                </div>
            );
        }
        return (
            <div class="greetings" >
              <span class="welcome">Welcome ${this.userName}</span>
            </div>
        );
    },
    
}


</script>

<style>

</style>