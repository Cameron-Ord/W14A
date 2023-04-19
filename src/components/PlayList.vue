<template>
    <div class="playlist_parent">

        <span>

            <button v-for="(playlist_song, i) in playlist_songs" :key="i" @click="play_song">{{ playlist_song.title }} - {{ playlist_song.artist }}</button>

        </span>

    </div>
</template>

<script>
    export default {


        props:{





        },


        data() {
            return {
                playlist_songs:[{}]
            }
        },


        methods:{


            play_song(){

                this.$emit(`play_song`, this.playlist_song);
            }


        }
    }
</script>

<style scoped>

</style>