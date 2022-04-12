<template>
  <div class="page">
    <v-app-bar
      color="transparent"
      class="appBar"
      flat
    >
      <v-spacer></v-spacer>
      <v-app-bar-nav-icon>
        <v-icon color="blue">mdi-menu</v-icon>
      </v-app-bar-nav-icon>
      <v-app-bar-nav-icon>
        <v-icon color="blue">mdi-menu</v-icon>
      </v-app-bar-nav-icon>
      <v-app-bar-nav-icon>
        <v-icon color="blue">mdi-menu</v-icon>
      </v-app-bar-nav-icon>

    </v-app-bar>
    <div style="height: 100%" class="parentDiv">
      <div class="mb-16 ml-16">
        <h1
          style="font-size:80px;color: aqua;"
          class="pb-0"
        >Sheak sadi</h1>
        <h2 class="pl-2">Front-end Developer</h2>
      </div>



    </div>


  </div>
</template>

<script>


export default {
  name: 'IndexPage',
  mounted() {
    document.body.style.overflow = 'hidden';

  }
}
</script>

<style scoped>
.page {
  width: 100vw;
  height: 100vh;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 999;
  overflow: hidden;

}

.appBar {
  justify-content: left !important;

}

.nameCard {
  /*filter: blur(10px);*/
  background-color: rgba(255, 255, 255, 0.2);
}

.parentDiv {
  display: flex;
  align-items: center;
}
</style>
