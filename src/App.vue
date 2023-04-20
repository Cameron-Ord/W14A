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


          <song-list @choose_song="chosen_song"></song-list>


        </article>
        <article class="article_playlist">

          <play-list :chosen_songs="chosen_songs"></play-list>

        </article>
        <article class="article_playing">


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

<script>
import SongList from './components/SongList.vue';
import PlayList from './components/PlayList.vue';
export default {


data() {
  return {
   
    chosen_songs: []

  }
},


  methods:{


    chosen_song: function(song){

      if(song !== undefined){


      this.chosen_songs.push(song);
      

      console.log(`i work`);


      }else{

        console.log(`i dont work`);

      }

      

    }

  },




  name: 'App',
  components: {
 
    SongList,
    PlayList

  }
}
</script>

<style>

*{

padding: 0px;
margin: 0px;

}


.apex_parent{


  display: grid;

  justify-items: center;

  align-items: center;

}

.apex_parent>.page_header{

  display: grid;

  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  justify-items: center;

  align-items: center;

  min-height: 10vh;


}

.apex_parent>.page_header>span{


  display: grid;

  align-items: center;

  justify-items: center;

  grid-template-columns: 40vw 40vw;


}


.apex_parent>.page_main{
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  display: grid;

  align-items: center;

  justify-items: center;

  min-height: 80vh;

}


.apex_parent>.page_footer{
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));

  display: grid;

  min-height: 10vh;
 
  align-items: center;

  justify-items: center;
 

}

.apex_parent>.page_footer>span{

  display: grid;

  align-items: center;

  justify-items: center;

  grid-template-columns: 1fr 1fr;

  text-align: center;

}
</style>
