<template>
    <div class="playing_parent">

        <!--if display_current title/aritst/image_url are all defined, then it will display the imported data from app-->
        <span v-if="display_current.title !==undefined" class="playing_span">


            <h3 v-if="display_current.title !==undefined" >{{ display_current.title }}</h3>

            <h3 v-if="display_current.artist !==undefined" >{{ display_current.artist }}</h3>

            <img v-if="display_current.image_url !==undefined" v-bind:src="display_current.image_url">
            

        </span>
    
    </div>
</template>

<script>
    export default {


        //receiving the object from App.vue//
    
        props:{

            display_current: Object,
         
        },


        data() {
            return {
                


            }
        },


        methods:{



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