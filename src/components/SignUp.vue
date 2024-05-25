<template>
    <nav>
      <div @click="goToHomePage" class="logo">
        <img src="../assets/logo.jpg" alt="Logo">
      </div>
      <div class="links">
        <ul>
          <li>
            <router-link to="/">Make a CV</router-link>
            <div class="submenu">
              <ul>
                <li><router-link to="/templates">CV Editor</router-link></li>
                <li><router-link to="/examples">Resume Examples</router-link></li>
                <li><router-link to="/examples">CV by artificial intelligence</router-link></li>
              </ul>
            </div>
          </li>
          <li><router-link to="/about">Candidacy</router-link></li>
          <li><router-link to="/contact">Advice</router-link></li>
          <li><router-link to="/signup">For The Pros</router-link></li>
        </ul>
      </div>
      <div class="buttons">
        <button class="buttons-2" @click="goToLogin">CONNECTION</button>
      </div>
    </nav>
    <div class="signup-container">
        <div class="form">
            <form @submit.prevent="signUp">
                <h2>Sign Up</h2>
                <div class="form-content">
                    <div class="form-name">
                        <label for="name">Fullname</label>
                    <input id="name" v-model="name" type="text" class="form-input" placeholder="Enter your name"  autocomplete="name"/>
                    </div>
                    <div class="form-email">
                        <label for="email">Email</label>
                        <input id="email" v-model="email" type="email" class="form-input" placeholder="Enter your email" autocomplete="email" />
                    </div>
                    <div class="form-password">
                        <label for="password">Password</label>
                        <input id="password" v-model="password" type="password" class="form-input" placeholder="Enter password"  autocomplete="new-password"/>
                    </div>
                    <div class="form-btn">
                        <button type="submit">CREATE MY ACCOUNT</button>
                    </div>
                </div>
            </form>
        </div>
        <div class="signup-container-content2">
            <img src="../assets/cv.webp" alt="Logo">
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    export default{
        name: "SignUp",
        data(){
            return{
                name: '',
                email: '',
                password: ''
            }
        },
        methods:{
            
            goToHomePage(){
            this.$router.push({ name: 'HomePage'});
            },
            async signUp(){
                let result = await axios.post("http://localhost:3000/user", {
                    email: this.email,
                    password: this.password,
                    name: this.name
                })
                console.log(result);
                if(result.status == 201){
                    alert("Successfull");
                    localStorage.setItem("user-info", JSON.stringify(result.data))
                }
            }
        }
    }
</script>

<style>
    .signup-container{
        display: flex;
        gap: 70px;
        margin: 40px 200px 40px 200px;
    }
    .form h2{
        color: #000000;
        margin: 30px 0 40px 0;
    }
    .form{
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 50px;
        background: #fff;
        padding: 50px;
    }
    
    .form-content{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        padding: 10px;
        gap: 20px;
        margin-bottom: 20px;
    }

    .form-name, .form-email, .form-password{
        display: flex;
        gap: 10px;
        width: 400px;
        align-items: center;
        justify-content: center;
    }
    .form-name input, .form-email input, .form-password input{
        width: 400px;
        height: 22.5px;
    }
    .form-name label, .form-email label, .form-password label{
        color: #000000;
        font-size: 16px;
    }
    .form-email input{
        margin-left: 26px;
    }
    .form-password input{
        margin-left: -5px;
    }
    .logo{
        width: 90px;
        height: auto;
    }
    .logo-title{
        margin-bottom: 20px;
        font-size: 32px;
    }
    .form-btn{
        margin-top: 20px;
    }
    .form-btn button{
        background-color: rgb(238, 176, 204);
        color: rgba(250, 42, 137, 1);
        padding: 15px;
        border: none;
        border-radius: 3px;
        cursor: pointer;
        font-size: 1.0rem;
        line-height: 1.2;
        font-weight: 700;
    }
    .form-btn button:hover{
        border: solid 1px rgba(250, 42, 137, 1);;
    }
</style>
