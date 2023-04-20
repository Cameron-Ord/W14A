<template>
    <div class="playing_parent">

        <span class="playing_span">


            <h3>{{ display_current.title }}</h3>

            <h3>{{ display_current.artist }}</h3>

            <img v-bind:src="display_current.image_url">
            

        </span>
    
    </div>
</template>

<script>
    export default {

        


        props:{

            display_current: Object,
         
        },


        data() {
            return {
                


            }
        },




        }



        

    
</script>

<style scoped>
.playing_parent{

display: grid;

justify-items: center;

align-items: center;

text-align: center;

width: 100%;
}

.playing_parent>.playing_span{
display: grid;

justify-items: center;

align-items: center;

text-align: center;

grid-template-rows: 5vh 5vh 1fr;

background-color: #A3CEF1;

width: 90%;

padding-top: 50px;

padding-bottom: 50px;

border-radius: 25px;
}

.playing_parent>.playing_span>img{

    height: 250px;
    width: 250px;

}
</style>