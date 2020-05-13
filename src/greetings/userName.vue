<script>
export default {
    data() {
     return {
         userName:''
     }
    },
    methods:{
        askForname() {
            return <div>
                     <input value={this.userName} placeholder = "Write your name" />
                     <span class="add_icon" onChange = {this.addUsername}>
                        <i class="far fa-plus-square"></i>
                     </span>
                   </div> 
        },
        paintGreetings(){
            return <div>
                     <p> Welcome {this.userName}! </p>
                     <span class="modify_icon" onChange = {this.modifyUsername}>
                        <i class="far fa-plus-square"></i>
                     </span>
                   </div>
        },
        addUsername(userName){
            localStorage.setItem(userName,userName);
        },
        modifyUsername(userName){
            localStorage.removeItem(userName);
            this.addUsername();
        },
        loadUsername(){
            if(this.userName === ''){
              return this.askForname(); 
            } else {
               return  this.paintGreetings();
            }

        }
    },
     render(){
        return(
            this.loadUsername()
        )
      }
   
    }

</script>
