
<template>
    <div>
 <v-stepper v-model="numStep">
     <v-stepper-header>
                <v-stepper-step :complete="numStep > 1" step="1">
                    Step1
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 2" step="2">
                    Step2
                </v-stepper-step>
                 <v-divider></v-divider>
                <v-stepper-step :complete="numStep > 3" step="3">
                    Step3
                </v-stepper-step>
    </v-stepper-header>
      <v-stepper-items>

        <v-stepper-content step="1">   
     <form>
         <div class="container">
        <h1>Register</h1>
        <p>Please fill in this form to create an account.</p>
        <hr>
          <label for="email"><b>Email</b></label>
          <input v-model ="email" type="text" placeholder="Enter Email" name="email" required>
          <label for="name"><b>Name</b></label>
          <input v-model="name" type="text" placeholder="Enter Name" name="name" required>
          <label for="surname"><b>Surname</b></label>
          <input v-model="surname" type="text" placeholder="Enter Surname" name="surname" required>
          <p>{{Error}}</p>
          <div class="button" @click="click_button1">Next</div>
         </div>
    </form>
        </v-stepper-content>

            <v-stepper-content step="2">
     <form>
        <div class="container">
        <h1>Password</h1>
        <p>Please fill in this form to create an account.</p>
        <hr>

    <label for="psw"><b>Password</b></label>
    <input v-model="password" type="password" placeholder="Enter Password" name="psw" required>
    <label for="psw-repeat"><b>Repeat Password</b></label>
    <input v-model="password2" type="password" placeholder="Repeat Password" name="psw-repeat" required>
    <hr>
    <p>{{Error}}</p>
    <div class="button" @click="click_button2">Next</div>

  </div>
</form>        
 </v-stepper-content>
            <v-stepper-content step="3">
               <form>
        <div class="container">
        <h1>Добро пожаловать!</h1>
        <h3>Ваш аккаунт создан</h3>
        <hr>
                         <p>Ваш email:{{email}} </p>
                         <p>Ваше имя: {{name}}</p>
                         <p>Ваша фамилия: {{surname}}</p>
                        <div class="button" @click="click_reset">Move Back</div>
  </div>
</form>
            </v-stepper-content>
        </v-stepper-items>
        </v-stepper>
  </div>
   
</template>


<script >

export default {            
    name: 'Stepper1',

    data: function(){
    return { 
      //  currentTab:0,
        name:"",
        surname:"",
        email:"",
        password:"",
        password2:"",
        Error:"",
        numStep: 1
    }
      
    },
    methods:{
click_button1: function() {

    if(this.name==""||this.surname==""||this.email=="")
      this.Error = "Enter your data"

    else
     {
        this.numStep = this.numStep+1
        this.Error=""
     }
},
click_button2: function() {

   if((this.password==""||this.password2=="")||(this.password!=this.password2))
      this.Error = "Enter password or your passwords not qual"    
  else
    {
      this.numStep = this.numStep+1
      this.Error=""
    }
    
},
click_reset : function() {
    this.numStep=1
    this.email=""
    this.name=""
    this.surname=""
    this.password=""
    this.password2=""
}, 


}
}
</script>
<style scoped>
* {box-sizing: border-box}

/* Add padding to containers */
.container {
    padding: 16px;
    background-color: #1e1e1e;
    border-radius: 20px;
    box-shadow: 0 3px 1px -2px rgba(0,0,0,.2), 0 2px 2px 0 rgba(0,0,0,.14), 0 1px 5px 0 rgba(0,0,0,.12);
}

/* Full-width input fields */
input[type=text], input[type=password] {
  width: 100%;
  padding: 15px;
  margin: 5px 0 22px 0;
  display: inline-block;
  border: none;
  background: #303030;
  color:#ffb9b9;
  border-radius: 20px;
  box-shadow: 0 3px 1px -2px rgba(0,0,0,.2), 0 2px 2px 0 rgba(0,0,0,.14), 0 1px 5px 0 rgba(0,0,0,.12);
}

input[type=text]:focus, input[type=password]:focus {
  background-color:#303030;
  outline: none;
  color: #ffb9b9;
  border-radius: 50px;
}

/* Overwrite default styles of hr */
hr {
  border: double;
  margin-bottom: 25px;
  color: #ffb9b9;
}

/* Set a style for the submit/register button */
.button {
  background-color: #404040;
  border-radius: 20px;
  color: #ffb9b9;
  padding: 16px 20px;
  margin: 8px 0;
  cursor: pointer;
  width: 100%;
  opacity: 0.9;
  box-shadow: 0 3px 1px -2px rgba(0,0,0,.2), 0 2px 2px 0 rgba(0,0,0,.14), 0 1px 5px 0 rgba(0,0,0,.12);
}

.registerbtn:hover {
  opacity:1;
}

/* Add a blue text color to links */
a {
  color: #ffb9b9;
}

/* Set a grey background color and center the text of the "sign in" section */
.signin {
  background-color: #1e1e1e;
  text-align: center;
}

.theme--light.v-stepper .v-stepper__header .v-divider {
    border-color: #ffb9b9;
}

.v-application .primary {
  background-color: #ca4d4d  !important;
    box-shadow: 0 3px 1px -2px rgb(0 0 0 / 20%), 0 2px 2px 0 rgb(0 0 0 / 14%), 0 1px 5px 0 rgb(0 0 0 / 12%);
    border-color: #ffffff   !important ;
}
</style>