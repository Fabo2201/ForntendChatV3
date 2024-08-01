<template>
  <div class="background_login"> 
  <div class="caja1"></div>
   <div class="login">
    <div class="login_title"></div>
    <q-card class="my-card">
      <q-card-section class="bg-teal-10">
        <div class="text-h6 text-center text-white ">LOGIN</div>
        
      </q-card-section>
      <q-separator />

      <q-card-actions vertical>
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
        class="bg-teal-9 absolute-center btn_ingresar text-white">Ingresar</q-btn>
        <q-btn   icon="mdi-key"
        class="absolute-center btn_ingresar  text-green">Olvide mi contraseña</q-btn>
        
     
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
  margin-top: 50%;
  width: 90%;
  
}
.my-card {

  width: 100%;
max-width: 350px;
box-shadow: 5px 5px 10px 5px rgb(114, 114, 114);
border-radius: 10px;
}
  .background_login{
    margin-top: 0px;
    height: 700px;
    width: 100%;
   
  }
  .login{
    height: 60%;
    display: flex;
    justify-content: center;
    align-content: center;

    width: 500px;
    margin: 0 auto;
  }
  .caja1{
    height: 20%;

  }
   .caja2{
    height: 20%;
   }

</style>