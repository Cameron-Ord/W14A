<template>
  <div class="apex_parent">
    <header class="page_header">
      <span>
        <h1>LOGO</h1>

        <h1>MENU</h1>
      </span>
    </header>

    <main class="page_main">
      <section class="section_main">
        <article class="article_songlist">

          <!--passing and receiving objects and arrays-->

          <song-list @choose_song="chosen_song_function"></song-list>


        </article>
        <article class="article_playlist">

          <play-list @play="current_obj" :chosen_songs="chosen_songs"></play-list>

        </article>
        <article class="article_playing">

          <now-playing :display_current="display_current"></now-playing>

        </article>
      </section>
    </main>

    <footer class="page_footer">
      <span>
        <p>placeholder footer text</p>
        <p>placeholder footer text</p>

      </span>
    </footer>
  </div>
</template>

<!--importing the components-->
<script>
import SongList from './components/SongList.vue';
import PlayList from './components/PlayList.vue';
import NowPlaying from './components/NowPlaying.vue';
export default {


  data() {
    return {

      //data for the passed objects//

      chosen_songs: [],


      display_current: {}


    }
  },


  methods: {

    //pushing the passed object song into the chosen_songs array//


    chosen_song_function: function (song) {

      if (song.src !== undefined) {


        this.chosen_songs.push(song);

        //console logs for debugging if it is undefined//

        console.log(`i work`);


      } else {

        console.log(`i dont work`);

      }



    },

    //taking the passed current object from the PlayList component, checking if it's defined,//

    //then, if it is defined, it will be equal to the display_current object//

    current_obj(current) {

      if (current.title !== undefined) {


        console.log(`current obj not undefined`);

        this.display_current = current;

      } else {

        console.log(`undefined current obj`);
      }


    }

  },




  name: 'App',
  components: {

    SongList,
    PlayList,
    NowPlaying

  }
}
</script>

<style>
* {

  padding: 0px;
  margin: 0px;

}

body {


  background-color: #E7ECEF;
}

.apex_parent {


  display: grid;

  justify-items: center;

  align-items: center;

}

.apex_parent>.page_header {

  display: grid;

  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  justify-items: center;

  align-items: center;

  min-height: 10vh;

  background-color: #A3CEF1;

  width: 100%;

}

.apex_parent>.page_header>span {


  display: grid;

  align-items: center;

  justify-items: center;

  grid-template-columns: 40vw 40vw;


}


.apex_parent>.page_main {
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  display: grid;

  align-items: center;

  justify-items: center;

  min-height: 80vh;

  width: 100%;
}

.apex_parent>.page_main>.section_main {

  display: grid;

  grid-auto-flow: row;

  align-items: center;

  justify-items: center;

  width: 100%;

  margin-bottom: 50px;
}

.apex_parent>.page_main>.section_main>.article_playing {

  display: grid;

  align-items: center;

  justify-items: center;

  width: 100%;

  margin-top: 25px;

  margin-bottom: 25px;



}

.apex_parent>.page_main>.section_main>.article_songlist {


  margin-top: 25px;

  display: grid;

  align-items: center;

  justify-items: center;

  width: 100%;
}

.apex_parent>.page_main>.section_main>.article_playlist {

  margin-top: 25px;

  margin-bottom: 25px;

  display: grid;

  align-items: center;

  justify-items: center;

  width: 100%;
}

.apex_parent>.page_footer {

  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  display: grid;

  min-height: 10vh;

  align-items: center;

  justify-items: center;

  background-color: #A3CEF1;

  width: 100%;


}

.apex_parent>.page_footer>span {

  display: grid;

  align-items: center;

  justify-items: center;

  grid-template-columns: 1fr 1fr;

  text-align: center;


}
</style>
