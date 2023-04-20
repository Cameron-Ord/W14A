<template>
    <div class="playlist_parent">

        <span>

            <button class="play_song_send" :play_song="i" v-for="(chosen_song, i) in chosen_songs" :key="i" @click="play(chosen_song)">{{ chosen_song.title }} - {{ chosen_song.artist }}</button>

        </span>

    </div>
</template>

<script>

    export default {

        data() {
            return {
            

                current: {},

                index: 0,

                isPlaying: false,

                player: new Audio()


            }
        },

        props:{



            chosen_songs: Array,



        },





        methods:{


            play(chosen_song){


                if(typeof chosen_song.src !== undefined){

                    console.log(`defined`);


                    this.current = chosen_song;


                    this.player.src = this.current.src;



                }

                this.player.play();
                this.isPlaying = true;

                if(typeof this.current.title !==undefined){

                
                    this.$emit(`play`, this.current);
                    console.log(`nowplaying sent current`);


                }

                this.current = this.chosen_songs[this.index];

            }


                },


            }


        
    
</script>

<style scoped>

</style>