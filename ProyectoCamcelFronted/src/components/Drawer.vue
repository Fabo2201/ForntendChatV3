<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="principal">
   <q-layout
      
      container
      style="height: 100vh"
      class="menu_vertical"
    >
      <q-drawer
        v-model="drawer"
        show-if-above
        :mini="miniState"
        @mouseover="miniState = false"
        @mouseout="miniState = true"
        mini-to-overlay
        :width="200"
        :breakpoint="10"
        bordered
        :class="$q.dark.isActive ? 'bg-teal-10' : 'bg-teal-10'"
        v-if="!isMobile"      
        >
        <q-scroll-area
        
          style="
            height: calc(100% - 150px);
            margin-top: 150px;
            
          "
        >
          <q-list padding>
            <q-item clickable v-ripple v-for="(boton , index) in botones"
            :key="index"  @click="pagina(boton.pagina)">
              <q-item-section  avatar>
                <q-icon style="color: blanchedalmond;" :name="boton.icono" />
              </q-item-section>

              <q-item-section style="color: blanchedalmond;"> {{ boton.nombre }} </q-item-section>
            </q-item>
          </q-list>
            
        </q-scroll-area>

        <q-img
          class="absolute-top grey-11 content-center"
          
          style="height: 150px"
        >
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="img-avatar content-center" v-show="!miniState">
              <img
                src="https://randomuser.me/api/portraits/women/68.jpg"
                class="img-avatar"
              />
            </q-avatar>
            <div class="text-weight-bold" v-show="!miniState">
              Stacey Howard
            </div>
          </div>
        </q-img>
      </q-drawer>

      <q-footer class="q-pa-none bg-teal-10" v-if="isMobile">
        <q-toolbar class="justify-around">
          <q-btn
            v-for="(boton, index) in botones"
            :key="index"
            @click="pagina(boton.pagina)"
            flat
            round
            class="column items-center"
          >
            <q-icon :name="boton.icono" size="24px" class="q-mb-xs" />
            <div class="text-caption">{{ boton.nombre }}</div>
          </q-btn>
        </q-toolbar>
      </q-footer>
      <q-container style="    padding-left: 58px;
      /* padding-top: 10px; */
      position: fixed;">
      </q-container>
    
    </q-layout>
     
  </div>
</template>

<script setup>
  import { ref, onMounted, onBeforeUnmount } from "vue";
  import { useRouter } from "vue-router"
  import footer from 'src/components/Footer.vue';
  
  const router = useRouter()
  const drawer = ref(false)
  const miniState = ref(true)
  const isMobile = ref(window.innerWidth <= 600);
  const botones = ref([
    {nombre:"Empresas",icono:"mdi-office-building-cog-outline",pagina:"/empresas" },
    {nombre:"Documentos",icono:"mdi-file",pagina:"/documentos" },
    {nombre:"His.Trabajo",icono:"mdi-folder-multiple",pagina:"/his.trabajo" },
    {nombre:"Calendario",icono:"mdi-calendar",pagina:"/calendario" },
    {nombre:"Soporte",icono:"mdi-cog-outline",pagina:"/soporte" },
    
  ])
  const pagina =(e)=>{
    router.push(e)
  }
  const handleResize = () => {
  isMobile.value = window.innerWidth <= 600;
};

onMounted(() => {
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("resize", handleResize);
});
</script>
<style scoped>
.q-pa-md {
  padding: 0px;
  margin-top: 0px;
}
@media (max-width: 600px) {
  .q-page-container {
    margin-left: 0;
  }

  /* Style adjustments for mobile view */
  
  .q-footer {
    position: fixed;
    bottom: 0;
    width: 100%;
   
  }
}
.img-avatar {
  display: flex;
}
.absolute-full,
.fullscreen,
.fixed-full {
  top: 50px;
  right: 0;
  bottom: 0;
  left: 0;
}

.principal{
  position: fixed;
  height: 100vh;
  width: 100%;
  z-index: 1;
 
}
.q-layout__section--marginal{
  background-color: bg-teal-10;
}


</style>
