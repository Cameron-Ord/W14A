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

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`

                },

              {


                    title: `Roller Mobster`,

                    artist: `Carpenter Brut`,

                    song_id: 91231,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`

                },

                {


                    title: `Roller Mobster`,

                    artist: `Carpenter Brut`,

                    song_id: 82811,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`

                },

                {


                    title: `Roller Mobster`,

                    artist: `Carpenter Brut`,

                    song_id: 75312,

                    image_url: `https://m.media-amazon.com/images/I/51PHl1VZO3L._AC_SX342_.jpg`

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

</style>