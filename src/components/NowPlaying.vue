<template>
    <div>

        <span>


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

</style>