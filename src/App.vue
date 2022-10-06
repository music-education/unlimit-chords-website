<template>

<!--     <header>
      <Menu></Menu>
    </header> -->

  <Menu />
  <div>
<!--       <div :style="{ 'margin-left': menuWidth }"> -->
    <router-view />
  </div>
    <!-- <ion-split-pane content-id='main'> -->
<!--         <Menu></Menu> -->
    <!-- </ion-split-pane> -->

</template>

<script lang="ts">


import { defineComponent } from 'vue';
import Menu from './components/Menu.vue';
// import menuWidth from '@/components/state';

export default defineComponent({
  name: 'App',
  components: {
    Menu
  },
  setup() {
    return {
      // menuWidth
    }
  }
})
</script>