<template>
    <div>
        <v-col cols="auto">
            <v-card v-on:click="openPhoto">
                <v-card-title>
                    {{ photo.id }}
                </v-card-title>
                <v-card-text>
                    <v-img
                        width="150"
                        height="150"
                        v-bind:src="photo.url"
                    />
                </v-card-text>
            </v-card>
        </v-col>
    </div>
</template>
<script>

export default {
    props: {
        photo: {
            type: Object,
            required: true
        }
    },
    methods: {
        openPhoto() {
            this.$emit('openPhoto', this.photo)
        }
    }
}
</script>
