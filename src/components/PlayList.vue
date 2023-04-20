<template>
    <div class="playlist_parent">

        <span class="funny_span">

        <span class="button_playlist">

            <!--a loop that will create a button and display a song title and artist for each object the array chosen_songs contains-->

              <!-- also calls the play function on click-->
            <button class="play_song_send" :play_song="i" v-for="(chosen_song, i) in chosen_songs" :key="i" @click="play(chosen_song)">{{ chosen_song.title }} - {{ chosen_song.artist }}</button>



        </span>

        <span class="information">

            <!-- some if statements that display depending on false or true values-->


            <h2 class="variable" v-if="!song_selected">Pick a song</h2>

            <h2 class="variable" v-else-if="paused_aspect"> Paused </h2>

            <p class="variable" v-else-if="song_selected">Now Playing</p>


        </span>
        <span class="controls">

            <!-- a play and pause button that change the values of variables affecting what messages are shown, and pausing/playing audio-->

            <button>PREV</button>

            <button v-if="!isPlaying" @click="play_button">PLAY</button>

            <button v-else-if="!paused_aspect" @click="pause">PAUSE</button>

            <button>NEXT</button>

        </span>
    </span>
    </div>
</template>

<script>

    export default {

        data() {
            return {
            
                //data containing variables and objects//

                current: {},

                index: 0,

                isPlaying: false,

                player: new Audio(),

                paused_aspect: false,

                song_selected: false,

            }
        },

        props:{


            //the passed array from App.vue//

            chosen_songs: Array,



        },





        methods:{

            //if chosen_song.src is not undefined, changes values //
         

            play(chosen_song){


                if(typeof chosen_song.src !== undefined){

                    console.log(`defined`);


                    this.current = chosen_song;


                    this.player.src = this.current.src;


                    this.paused_aspect = false;


                    this.song_selected = true;

                }

                //if current.title is defined, it will emit the current object, which is then sent to NowPlaying//

                if(typeof this.current.title !==undefined){

                
                    this.$emit(`play`, this.current);
                    console.log(`nowplaying sent current`);


                }

                //making the song play, and changing the isPlaying variable to true last// 

                this.current = this.chosen_songs[this.index];

                this.player.play();
                
                this.isPlaying = true;

            


            },

            //a simple play button seperate from the buttons on the playlist//

            play_button(){

                this.paused_aspect = false;
                this.player.play();
                this.isPlaying = true;
            },

            //a pause button that changes respecting values//
            pause(){


                this.player.pause();
                this.isPlaying = false;
                this.paused_aspect = true;

            },


                },


            }


        
    
</script>

<style scoped>


.playlist_parent{

display: grid;

width: 100%;

justify-items: center;

align-items: center;

text-align: center;



}


.variable{

display: grid;

margin-top: 20px;

margin-bottom: 20px;

}
.playlist_parent>.funny_span{
    display: grid;

    justify-items: center;

    align-items: center;

    text-align: center;

    width: 90%;

    background-color: #A3CEF1;
    
    grid-auto-flow: row;

    padding-top: 50px;

    padding-bottom: 50px;

    border-radius: 25px;

}

.playlist_parent>.funny_span>.button_playlist{

display: grid;

justify-items: center;

align-items: center;

text-align: center;

grid-auto-flow: row;

width: 90%;



}

.playlist_parent>.funny_span>.button_playlist>button{
    margin-bottom: 5px;
    margin-top: 5px;
    height: 50px;
    width: 90%;
}

.playlist_parent>.funny_span>.information{

display: grid;

justify-items: center;

align-items: center;

text-align: center;

width: 90%;
}

.playlist_parent>.funny_span>.controls{

display: grid;

justify-items: center;

align-items: center;

text-align: center;

grid-template-columns: 1fr 1fr 1fr;

width: 90%;


}
.playlist_parent>.funny_span>.controls>button{
    margin-bottom: 5px;
    margin-top: 5px;
    height: 50px;
    width: 80%;
}
</style>