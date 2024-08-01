<template>
  <div class="background_login"> 
  <div class="caja1"></div>
   <div class="login">
    <div class="login_title"></div>
    <q-card class="my-card">
      <q-card-section class="bg-teal-10">
        <div class="text-h6 text-center text-white ">REGISTRO</div>
        
      </q-card-section>
      <q-separator />

      <q-card-actions vertical>
        <q-input bottom-slots v-model="text" label="Nombre de usuario" counter maxlength="15" :dense="dense"></q-input>
        <q-input bottom-slots filled v-model="email" suffix="@gmail.com" label="Correo" counter maxlength="35" :dense="dense"></q-input>
      <q-input bottom-slots counter maxlength="20" v-model="password" label="Contraseña" filled :type="isPwd ? 'password' : 'text'" ><template v-slot:append>
            <q-icon
              :name="isPwd ? 'visibility_off' : 'visibility'"
              class="cursor-pointer"
              @click="isPwd = !isPwd"
            />
          </template>
        </q-input>
        <q-input bottom-slots counter maxlength="20" v-model="password" label="Repetir Contraseña" filled :type="isPwd ? 'repeat-password' : 'text'" >
          <template v-slot:append>
            <q-icon
              :name="isPwd ? 'visibility_off' : 'visibility'"
              class="cursor-pointer"
              @click="isPwd = !isPwd"
            />
            
          </template>
        </q-input>
        <q-btn flat icon="mdi-key"
          class="btn_ingresar">Registrarse</q-btn>
     
      </q-card-actions>
    </q-card>

   
    </div>
    <div class="caja2"></div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      text: ref(''),
      password: ref(''),
      isPwd: ref(true),
      dense: ref(false)
    }
  }
}

   


</script>
<style scoped>

.btn_ingresar{
  margin-top: 10%;
  width: 90%;
  
}
.my-card {
  height: fit-content;
  width: 100%;
max-width: fit-content;
box-shadow: 5px 5px 10px 5px rgb(114, 114, 114);
border-radius: 10px;
}
  .background_login{
    margin-top: 0px;
    height: 700px;
    width: 100%;
    
  }
  .login{
    height: 65%;
    display: flex;
    justify-content: center;
    align-content: center;

    width: 500px;
    margin: 0 auto;
  }
  .caja1{
    height: 15%;

  }
   .caja2{
    height: 20%;
   }
  

 

</style>
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 <!--<template>
    <div class="background_login"> 
    <div class="caja1"></div>
     <div class="login">
      <div class="login_title"></div>
      <q-card class="my-card">
        <q-card-section>
          <div class="text-h6 text-center ">REGISTRO</div>
          
        </q-card-section>
        <q-separator />
  
        <q-card-actions vertical>
            <q-input bottom-slots v-model="text" label="Nombre de usuario" counter maxlength="15" :dense="dense"></q-input>
            <q-input bottom-slots filled v-model="email" suffix="@gmail.com" label="Correo" counter maxlength="35" :dense="dense"></q-input>
          <q-input bottom-slots counter maxlength="20" v-model="password" label="Contraseña" filled :type="isPwd ? 'password' : 'text'" >
            <template v-slot:append>
              <q-icon
                :name="isPwd ? 'visibility_off' : 'visibility'"
                class="cursor-pointer"
                @click="isPwd = !isPwd"
              />
            </template>
          </q-input>
          <q-btn flat icon="mdi-key"
          class="btn_ingresar">Registrarse</q-btn>
          
          
          
        </q-card-actions>
      </q-card>
  
      </div>
      <div class="caja2"></div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue'
  
  export default {
    setup () {
      return {
        text: ref(''),
        password: ref(''),
        isPwd: ref(true),
        dense: ref(false)
      }
    }
  }
  
     
  
  
  </script>
  <style scoped>
  .btn_ingresar{
    margin-top: 35%;
  }
  .my-card {
  
    width: 100%;
  max-width: 250px;
  }
    .background_login{
      background-color: var(--q-primary);
      margin-top: 0px;
      height: 700px;
      width: 100%;
    }
    .login{
      height: 60%;
      display: flex;
      justify-content: center;
      align-content: center;
    }
    .caja1{
      height: 20%;
  
    }
     .caja2{
      height: 20%;
     }
  
  </style>-->