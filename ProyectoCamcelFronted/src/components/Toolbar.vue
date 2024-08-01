<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="q-pa-md fixed-header">
    <div class="row no-wrap">
      
        
        
        
      <q-toolbar class="col-10 bg-teal-10 text-white">
        <q-btn flat round dense aria-setsize="100px">  </q-btn>
        <q-toolbar-title class="text-xs">Camcel</q-toolbar-title>
        
        
          <q-input class="col-8 bg-teal-10 text-white "  filled v-model="text"  label="Busqueda" >
            <template v-slot:prepend>
              <q-btn   flat round dense class="icono_de_busqueda text-indigo-1" icon="search"/>
            </template>
          </q-input>
          

        </q-toolbar>
        <q-toolbar class="col-2 bg-teal-10 text-white">
        <q-btn flat round dense icon="mdi-bell"/>
        <Chat/>
      
        <q-btn flat round dense class="q-pa-md" icon="mdi-menu" >
          <q-menu>
            <q-list style="min-width: 100px">
              <q-item clickable v-close-popup>
                <q-item-section>Perfil</q-item-section>
              </q-item>
              
              <q-separator />
              <q-item clickable v-close-popup>
                <q-item-section>Empresa</q-item-section>
              </q-item>

              <q-separator />
              <q-item clickable v-close-popup>
                <q-item-section>Documentos</q-item-section>
              </q-item>

              <q-separator />
              <q-item clickable v-close-popup>
                <q-item-section>Descargas</q-item-section>
              </q-item>

              <q-separator />
              <q-item clickable v-close-popup>
                <q-item-section>Configuracion</q-item-section>
              </q-item>

              <q-separator />
              <q-item clickable v-close-popup>
                <q-item-section>Cerrar Sesion</q-item-section>
              </q-item>

            </q-list>
          </q-menu>
        </q-btn>
  
        <!--<ul class="menu_vertical">
          <li>
          <RouterLink to="/perfil"><a>Perfil</a></RouterLink>
          </li> 
          <li>
          <RouterLink to="/login"><a>Login</a></RouterLink>
          </li> 
          <li>
          <RouterLink to="/registro"><a>Registro</a></RouterLink>
          </li> 
          <li>
          <RouterLink to="/cerrar"><a>Cerrar Sesion</a></RouterLink>
          </li> 

        </ul>-->
       
      </q-toolbar>
    </div>
  </div>
</template>

<style scoped>
.q-pa-md {
  padding: 0px 0px;
  
}
.row, .column, .flex {
  display: flex;
  /* flex-wrap: wrap; */
  justify-content: flex-end;
}
.borde-de-toolbar{
  
    border: 20px;
    border: groove rgb(49, 152, 248);
}
.fixed-header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000; /* Asegúrate de que el encabezado esté por encima de otros elementos */
  background-color: white; /* O el color que desees */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Para darle un pequeño sombreado */
}

</style>
<script>
import { ref } from 'vue'
import Chat from 'src/components/Chat.vue'

export default {
  components: { Chat },
  setup () {
    return {
      text: ref(''),
      dialog: ref(false),
      maximizedToggle: ref(true)
     
    }
  }
}
</script>