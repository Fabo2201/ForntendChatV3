<template>
    <q-btn flat round dense icon="mdi-chat" @click="dialog = true">
        
         <q-dialog
          v-model="dialog"
          persistent
          :maximized="maximizedToggle"
          transition-show="slide-up"
          transition-hide="slide-down">    
          
          
      <q-card class="bg-teal-10 text-white">
           <div class="header"> <ChatHedaer/> </div>
        
           <div class="TextArea"></div> 
         
       
        <div class="drawer"><DrawerChat/></div>
        <q-toolbar class="chat bg-grey-3 text-black ">
          
          <q-btn round flat icon="insert_emoticon" class="q-mr-sm" />
          <q-input rounded outlined dense class="BarraTexto q-mr-sm" bg-color="white" v-model="message" placeholder="Type a message" />
          <q-btn round flat icon="send" />
        </q-toolbar>
      </q-card>
    </q-dialog>
 </q-btn>
</template>
<style scoped>
.BarraTexto{
  width: 90%;
}
.TextArea{
  top: 6%;
  right: 0%;
  position: absolute;
  width: 75%;
  height: 90%;
  background-color: aquamarine;
  z-index: 1;
}
.header{
  width: 75%;
  height: 2%;
  position: relative;
  left: 25%;
  z-index: 2;
}
.q-dialog__inner--maximized > div {
    width: 80%;
    height: 80%;
    overflow-y:hidden

}

.chat{
right: 0%;
bottom: 0%;
position: absolute;
width: 75%;
height: 9%;
bottom: 0;
z-index: 4;
}
.drawer{
    width: 25%;
    height: 100%;
    background-color: white;
    color:#000 ;
   top: 0%;
    position: absolute;
    z-index: 3;
}
</style>
<script setup>
import { ref } from 'vue'
import DrawerChat from 'src/components/DrawerChat.vue'
import ChatHedaer from 'src/components/ChatHedaer.vue'

const text = ref('')
const dialog = ref(false)
const maximizedToggle = ref(true)

</script>