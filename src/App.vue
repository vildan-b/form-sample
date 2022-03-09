<template>
    <div class="container">
        <form>
        <div v-if="!isSubmitted">    
           <div class="row">
               <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
               <div class="col-md-12">
                             <appNamesurname v-model="fullname"></appNamesurname>

                  <div class="form-group">
                    <label for="email">E-Mail</label>
                    <input type="text" 
                    id="email" 
                    class="form-control" 
                    v-model="email"
                    >
                  </div>
                  <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password" 
                    id="password" 
                    class="form-control" 
                    v-model="password"
                    >
                  </div>
                </div>
                <div>
                <label> <input type="radio" value="Female" v-model="gender"> Female </label>
                <label> <input type="radio" value="Male" v-model="gender"> Male </label>

                </div>
                <button @click.prevent="submit()"> Sign up</button>
                </div>

                  
                   
                </div>
            </div>
        </form>
        <hr>
        <div v-if="isSubmitted" class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-info">
                    <div class="panel-heading">
                        <h4> Information You Entered</h4>
                    </div>
                    <div class="panel-body">
                        <p>Fullname: {{ fullname}} </p>
                        <p>E-mail: {{ email}}</p>
                        <p>Password: {{password}}</p>
                        <p>Gender: {{gender}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import NameSurname from './NameSurname'
    export default {
    
        data(){
            return{
                isSubmitted:false,
                    fullname:"",
                    email:"",
                    password:"",
                    gender:""
                
            }
        },
        methods:{
            submit(){
                this.isSubmitted = true;

            }
        },  
          components: {
            appNamesurname : NameSurname
        },   
      
    }
</script>

<style>
</style>
