<template>
    <div class="playlist_parent">

        <span>

            <button class="play_song_send" :play_song="i" v-for="(chosen_song, i) in chosen_songs" :key="i" @click="send_play">{{ chosen_song.title }} - {{ chosen_song.artist }}</button>

        </span>

    </div>
</template>

<script>

    export default {


        props:{



            chosen_songs: Array,



        },





        methods:{

            send_play: function(details){


                let button_class = document.querySelector(`.play_song_send`);


                let send_play = button_class.getAttribute(`play_song`);


                let chosen_song = this.chosen_songs[send_play];


                console.log(details);


                this.$emit(`send_play`, chosen_song);
                

                console.log(`playlist works`);

            }


        }
    }
</script>

<style scoped>

</style>