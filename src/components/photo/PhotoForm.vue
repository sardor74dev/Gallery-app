<template>
    <div>
        <v-container>
            <div class="flex">
                <v-text-field v-model="title"/>
                <v-file-input v-model="img"/>
            </div>
            <div>
                <v-btn 
                    class="mt-2 mb-2"
                    v-on:click="addPhoto">
                    Добавить
                </v-btn>
            </div>
        </v-container>
    </div>
</template>
<script>
//import { defineComponent } from '@vue/composition-api'

export default {
    data: () => ({
        title: '',
        img: null
    }),
    methods: {
        addPhoto() {
            const reader = new FileReader()
            reader.onload = () => {
                let photo = {
                id: Date.now(),
                title: this.title,
                url: reader.result
                }
                this.$emit('addPhoto', photo)
            }
            reader.readAsDataURL(this.img)
        }
    }
}
</script>
<style scoped>
.flex {
    display: flex;
}
@media( max-width: 992px ){
    .flex {
        display: block;
    }
}
</style>

