<template>
    <v-dialog
        v-model="dialogVisible"
        max-width="600"
    >
        <v-card>
            <v-card-title>
                {{"Photo name - " + photo.title }}
            </v-card-title>
            <v-card-text>
                <v-img 
                    v-bind:src="photo.url"
                >
                </v-img>
            </v-card-text>
        </v-card>
    </v-dialog>
</template>
<script>
export default {
    props: {
        photo: {
            type: Object,
            required: true
        },
        dialogVisible: {
            type: Boolean,
            default: false
        }
    },
    data: () => ({
    }),
   

}
</script>
