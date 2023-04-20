<template>
    <div class="playlist_parent">

        <span>

            <button v-for="(chosen_song, i) in chosen_songs" :key="i" @click="play">{{ chosen_song.title }} </button>

        </span>

    </div>
</template>

<script>
    export default {


        props:{



            chosen_songs: Array,



        },





        methods:{

            play: function(){



                

                console.log(`playlist works`);

            }


        }
    }
</script>

<style scoped>

</style>