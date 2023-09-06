<template >
    <SingleCocktail v-if="cocktail" class="single-cocktail w-50 mx-auto mb-4" 
            :image="cocktail.image"
            :title="cocktail.name"                      
            :content="cocktail.content"
            />
</template>
<script>
import axios from 'axios';
import SingleCocktail from '../components/SingleCocktail.vue'
export default {
    name: 'CocktailShow',
    components: {
        SingleCocktail
    },
    data() {
        return {
            apiUrl : 'http://127.0.0.1:8000',
            cocktail : false
        }
    },
    methods: {
        getSingleCocktail(){
            axios.get(`${this.apiUrl}/api/cocktails/${this.$route.params.id}`).then((response) => {
                console.log(response);
                this.cocktail = response.data.results;
            }).catch(function (error) {
                // handle error
                console.log(error);
            });
        }
    },

    created() {
        this.getSingleCocktail();
    },
}

</script>
<style lang="scss" scoped>
    article.single-cocktail{
        padding-top: 2rem;
        width: 100%;
        border-radius: 1rem;
        padding: 1rem;
        margin-right: 1rem;
        background-color: rgb(221, 221, 221);
        color: black;
        margin-bottom: 2rem;

        *{
            margin-bottom: 1rem;
        }

        img{
            width: 100%;
            height: 6rem;
            object-fit: cover;
        }

        h6 span{
            margin-right: 1rem;
        }

        &:hover{
            background-color: white;
        }
    }
</style>