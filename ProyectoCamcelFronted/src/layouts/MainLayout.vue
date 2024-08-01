<template>
  <q-layout view="lHh Lpr lFf">

  <Toolbar/>
  <Drawer/>
  <router-view/>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import Toolbar from 'src/components/Toolbar.vue';
import Drawer from 'src/components/Drawer.vue';

defineOptions({
  name: 'MainLayout'
})



const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
