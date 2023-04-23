<template>
    <div id="NewUserWrapper">
    <form class="NewUserForm" lang="en">
        <h1>Sign Up</h1>
        <label for="username">User Name: </label>
        <input class="NewUser" id="username" v-model="username"/><br>
        <label for="email" >Email Address: </label>
        <input class="NewUser" id="email" v-model="email"/><br>
        <label for="password">Enter Password: </label>
        <input class="NewUser" id="password" type="password" v-model="password"/><br>
        <label for="secondarypassword">Enter Password Again: </label>
        <input class="NewUser" id="secondarypassword" type="password" v-model="pw2"/><br>
        <button :disabled="btn" @click.prevent="submit()">Submit</button>
    </form>
    <p>{{ username }}<br>{{ email }}</p>
    </div>
</template>

<script>
//import axios from 'axios'
export default {
    name:'SignUpPage',
    data(){
        return{
            password:'',
            pw2:'',
            username:'',
            email:'',

        };
    },
    methods:{
        submit(){
           
          //axios.post("/api/1.0/users",{username:this.username,email:this.email,password:this.password})
          //using internal fetch props in vue
          const reqBody = {username:this.username,email:this.email,password:this.password};
          fetch("/api/1.0/users",{method:"POST", body: JSON.stringify(reqBody),headers: {"Content-Type":"application/json"}})
        }
    },
    computed:{
        btn()
        {
            return this.password && this.pw2? this.password!=this.pw2:true;
        }
    }
}
</script>
<style scoped>
#NewUserWrapper{
    width:70%;
    margin: 0 auto;
    justify-content: center;
    align-items: center;
}
.NewUserForm{
    width:30%;
    border-style: double;
    border-width:10px;
    border-radius: 50px;
    border-color: blue;
    background-color: greenyellow;
    background-origin: center;
   }
.NewUser{
    text-emphasis-color: blue;
    margin: 5px;
}
</style>