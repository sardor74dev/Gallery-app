<template>
  <v-card
    color="primary"
  >
  
      <v-app-bar
        color="primary"
      >
        <v-container class="ml-100">
          <v-app-bar-nav-icon color="white"></v-app-bar-nav-icon>

          <v-toolbar-title color="white">Photo Gallery</v-toolbar-title>
          <div class="h-items">
            <div class="h-item">
              <a><router-link to="/">Главная</router-link></a>
            </div>
            <div class="h-item">
              <a><router-link to="/photo">Фотографии</router-link></a>
            </div>
          </div>
          
        </v-container>
      </v-app-bar>
    
  </v-card>
</template>

<script>
export default {
  
}
</script>
<style scoped>
.h-item a {
  color: #fff;
  text-decoration: none;
}
.ml-100 {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.h-items {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.h-item {
  margin-right: 20px;
}
</style>
