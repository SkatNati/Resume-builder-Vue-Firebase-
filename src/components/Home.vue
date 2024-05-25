<template>
  <div>
    <nav>
      <div class="logo">
        <img @click="goToHomePage" src="../assets/logo.jpg" alt="Logo">
      </div>
      <div class="links">
        <ul>
          <li>
            <router-link to="/">Make a CV</router-link>
            <div class="submenu">
              <!-- Content of the submenu -->
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
        <button class="buttons-1" @click="goToSignUp">CREATE MY CV</button>
        <button class="buttons-2" @click="goToLogin">CONNECTION</button>
      </div>
    </nav>
    <div class="home-container">
      <div class="home-container-content1">
        <h1>Create your modern and professional CV online for free with CVDesignR.</h1>
        <p>I In just a few minutes, create your CV for free , choose a template, personalize its design, then download it as a PDF . Then browse targeted job offers and organize your applications.</p>
        <img src="../assets/stat.png" alt="Logo">
      <div class="home-container-content3">
        <button class="buttons-3" @click="goToSignUp">CREATE MY CV</button>
        <span>Free Registration</span>
      </div>
      </div>
      <div class="home-container-content2">
        <img src="../assets/cv.webp" alt="Logo">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  methods: {
    goToHomePage(){
      this.$router.push({ name: 'HomePage'});
    },
    goToSignUp() {
      this.$router.push({ name: 'SignUp' });
    },
    goToLogin() {
      this.$router.push({ name: 'Login' });
    }
  }
}
</script>

<style>
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #FFF;
  color: white;
}
.home-container{
  display: flex;
  gap: 70px;
  margin: 40px 200px 40px 200px;
}
.home-container-content1{
  display: flex;
  flex-direction: column;
  gap: 0px;
  justify-content: center;
}
.home-container-content1 h1{
  color: black;
  text-align: left;
  font-weight: bolder;
}
.home-container-content1 p{
  color: black;
  text-align: left;
  font-weight: 100;
}
.home-container-content1 img{
  width: 350px;
  margin-left: 30px;
}
.home-container-content2 img{
  width: 600px;
}
.home-container-content3{
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 30px;
  margin-left: -38px;
}
.home-container-content3 button{
  background-color: rgba(250, 42, 137, 1);
  color: white;
  padding: 15px;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  font-size: 1.0rem;
  line-height: 1.2;
  font-weight: 700;
}
.home-container-content3 span{
  color: black;
  font-size: 10px;
  margin-top: 4px
}
.logo img {
  max-width: 100px; 
}

.links ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.links ul li {
  margin-right: 5.25rem;
  position: relative;
}

.links ul li a {
  color: #605757;
  text-decoration: none;
  font-size: 0.95rem;
}

.submenu {
  position: absolute;
  top: 100%; /* Position it below the parent li */
  left: 0;
  background-color: #FFF;
  display: none; /* Hide initially */
}

.links ul li:hover .submenu {
  display: block; /* Show on hover */
}

.submenu ul {
  list-style-type: none;
  padding: 0;
}

.submenu ul li {
  padding: 10px;
}

.buttons-1, .buttons-2{
  background-color: rgb(238, 176, 204);
  color: rgba(250, 42, 137, 1);
  padding: 10px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 0.75rem;
  line-height: 1.2;
  font-weight: 700;
}

.buttons-2 {
  color: rgb(43, 171, 226);
  background-color: rgb(193, 224, 238);
  margin: 0 20px 0 20px;
}

.buttons-2:hover{
  border: solid 1.25px rgb(43, 171, 226);
}

.buttons-1:hover {
  border: solid 1.25px rgba(250, 42, 137, 1);
}
.submenu ul {
  list-style-type: none; 
  padding: 0;
  margin: 10px 0 0; 
  display: block; 
}

.submenu ul li {
  padding: 10px;
  border-top: 0.25px solid #efeeee; 
}

</style>
