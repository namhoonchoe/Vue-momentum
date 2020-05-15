<script>
export default {
    data() {
     return {
         userName:''
     }
    },
    
      methods:{
        askForname() {
            return <input type = "text" 
                          placeholder = "Write your name" 
                          value={this.userName}/>
        },
        paintGreetings(){
            return  <p> Welcome {this.userName}! </p>
        },
       
        getUsername(){
            this.userName = localStorage.getItem('userName');
        }, 

        saveUsername(text){
            this.getUsername();   
            localStorage.setItem('userName',text);         
        },

        modifyUsername(text){
            localStorage.removeItem('userName');
            this.saveUsername(text);
        },
        
    
    },
    render(){
        const currentUser = this.userName;
        if(currentUser === ''){
            return <div>
                      {this.askForname()}
                      <span class="add_icon" onClick={this.saveUsername}>
                         <i class="far fa-plus-square"></i>
                      </span> 
                    </div>
            } else {
            return <div>
               {this.paintGreetings()}
               <span class="modify_icon"
                     onClick={this.modifyUsername}>
                  <i class="far fa-plus-square"></i>
               </span>
             </div>
        }       
      }

   
    }

</script>
