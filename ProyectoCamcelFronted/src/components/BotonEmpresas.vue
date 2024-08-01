

<template>
  <div class="q-pa-md row justify-center scrollable-section" style="padding-top: 60px;">
    

    <q-card  class="my-card q-mr-md" flat bordered>
      <q-btn>
        <q-card-section class="q-pa-md text-center">
          <q-avatar  size="100px" class="q-mb-md" icon="mdi-plus-circle-outline" />
        
          <div class="text-body1 q-mb-md">Agregar empresa</div>
        </q-card-section>
        
        <q-card-section class="q-pa-md">
          <div class="text-caption text-grey">Con este boton se puede agregar empresas</div>
        </q-card-section>
        
        <q-card-section> 
          <div class="text-caption text-grey">Aca se ve si esta verificada o no <q-icon
            size="30px"
            /> 
          </div>
        </q-card-section>
      </q-btn>
    </q-card>
   
  <q-card v-for="empresa in empresas" :key="empresa.id" class="my-card q-mr-md" flat bordered>
    <q-btn>
      <q-card-section class="q-pa-md text-center">
        <q-avatar  size="100px" class="q-mb-md" >
          <img :src="empresa.imagen" />
        </q-avatar>
        <div class="text-body1 q-mb-md">{{ empresa.nombre }}</div>
      </q-card-section>
      
      <q-card-section class="q-pa-md">
        <div class="text-caption text-grey">{{ empresa.descripcion }}</div>
      </q-card-section>
      
      <q-card-section> 
        <div class="text-caption text-grey">{{ empresa.verificado ? "Verificado" : "No verificado" }} <q-icon
            :name="empresa.verificado ? 'check_circle' : 'cancel'"
            :color="empresa.verificado ? 'green' : 'red'"
            size="30px"
            />
          </div>
      </q-card-section>
      
     
    </q-btn>
  </q-card>


   
  
  </div>
</template>

<script setup>
import { ref } from "vue";
import empresasData from './datos.json';

const empresas = ref(empresasData)
</script>

<style scoped>
.my-card {
  width: 380px; /* ajusta el ancho de la tarjeta */
  height: auto; /* ajusta el alto de la tarjeta */
  margin-bottom: 20px; /* agrega un margen inferior a cada tarjeta */
  border-radius: 10px; /* agrega un borde redondeado a la tarjeta */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* agrega una sombra a la tarjeta */
}
.scrollable-section {
   /* Altura máxima deseada para la sección */
  overflow-y: auto; /* Habilitar barra de desplazamiento vertical cuando sea necesario */
  /* Otros estilos opcionales */
}
</style>



