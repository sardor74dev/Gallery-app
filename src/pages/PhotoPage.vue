<template>
    <div class="container">
        <v-container>
            <PhotoForm v-if="photos.length < 20" @addPhoto='addPhoto'/>
            <div v-else>Your image posting limited!</div>
                <v-row>
                    <Photo
                    v-for="photo in photos" :key="photo.title"
                    v-bind:photo="photo"
                    v-on:openPhoto="openPhoto"
                    />
                </v-row>
                <PhotoDialog :photo="currentPhoto" v-model="dialogVisible"/>
        </v-container>
    </div>
</template>
<script>
import Photo from "@/components/photo/Photo";
import PhotoForm from "@/components/photo/PhotoForm"
import PhotoDialog from "../components/photo/PhotoDialog.vue";
export default {
    components: {
    Photo,
    PhotoForm,
    PhotoDialog
},
    data: () => ({
        photos: [],
        currentPhoto: {},
        dialogVisible: false
    }),
    mounted() {
        this.fetchTodo()
    },
    methods: {
        fetchTodo() {
            this.axios.get('https://jsonplaceholder.typicode.com/photos?_limit=19')
            .then(response => this.photos = response.data)
        },
        addPhoto(photo) {
            this.photos.push(photo)
        },
        openPhoto(photo) {
            this.currentPhoto = photo
            this.dialogVisible = true
        }
    }
}
</script>
<style scoped>
.container {
    max-width: 1200px;
    padding: 15px;
}
/* @media (max-width: 1312px){
  .container {
    max-width: 1104px;
  }
} */
@media (max-width: 1200px){
  .container {
    max-width: 970px;
  }
}
@media (max-width: 992px){
  .container {
    max-width: 750px;
    /* font-size: 10px; */
  }
}
@media (max-width: 767px){
  .container {
    max-width: 537px;
    font-size: 8px;
  }
}
@media (max-width: 553px){
  .container {
    max-width: 333px;
  }
}
@media (max-width: 346px){
  .container {
    max-width: none;
  }
}
</style>
