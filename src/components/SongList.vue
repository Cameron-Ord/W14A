<template>
    <div class="songlist_parent">

        <span class="songlist">


            <button :clicked_song="i" v-for="(song, i) in songs" :key="i" @click="choose_song">{{ song.title }} - {{ song.artist }}</button>

            
        </span>

    </div>
</template>

<script>
    export default {

        

        data() {
            return {
                
                


                songs:[
                    
                {

                    title: `Roller Mobster`,

                    artist: `Carpenter Brut`,

                    song_id: 35251,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`,

                    src: require(`../assets/mobster.mp3`)

                },

              {


                    title: `Le perv`,

                    artist: `Carpenter Brut`,

                    song_id: 91231,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`,

                    src: require(`../assets/leperv.mp3`)

                },

                {


                    title: `Meet Matt Stryker`,

                    artist: `Carpenter Brut`,

                    song_id: 82811,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`,

                    src: require(`../assets/mattstryker.mp3`)

                },

                {


                    title: `Turbo Killer`,

                    artist: `Carpenter Brut`,

                    song_id: 75312,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`,

                    src: require(`../assets/turbokiller.mp3`)

                },
            
            ]


            }
        },

        methods:{



            choose_song: function(details){


    
               let button = details.currentTarget;


               let button_clicker = button.getAttribute(`clicked_song`);


               let song = this.songs[button_clicker];


                console.log(details);


                this.$emit(`choose_song`, song);
            },




        }


    }
</script>

<style scoped>
.songlist_parent{

    display: grid;

    width: 100%;

    justify-items: center;

align-items: center;

grid-template-rows: 50vh;

}

.songlist_parent>.songlist{

    background-color: #A3CEF1;

    display: grid;

    justify-items: center;

    align-items: center;

    grid-auto-flow: row;

    width: 90%;

    padding-top: 50px;

    padding-bottom: 50px;

    border-radius: 25px;
}

.songlist_parent>.songlist>button{


    margin-bottom: 5px;
    margin-top: 5px;
    height: 50px;
    width: 90%;
}
</style>