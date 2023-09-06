<template>
    <section class="projects-wrapper">
        <h1 class="main-title text-center">
            COCKTAILS
        </h1>
        <nav class="pagination flex-row mx-5 justify-content-between ">

            <div class="btn btn-primary"> 
                <span class="prev align-self-start" @click="prevPage" v-if="prevPageUrl">
                    Previous
                </span>
            </div>
            <div class="btn btn-primary">
                <span class="next align-self-end" @click="nextPage" v-if="nextPageUrl">
                    Next
                </span>
            </div>
        </nav>
        <div class="cocktails d-flex flex-wrap justify-content-center gap-4">
            <SingleCocktail class="single-project" v-for="cocktail in cocktailsList" 
            :image="cocktail.image"
            :title="cocktail.name"                      
            :content="cocktail.content"
            @click="$router.push({ name: 'cocktails.show', params: { id: cocktail.id} })"
            />
        </div>
    </section>
</template>
<script>
import axios from 'axios';
import SingleCocktail from '../components/SingleCocktail.vue';

export default {
    name: 'Cocktails',

    components: {
        SingleCocktail
    },

    data(){
        return{
            cocktailsList: [],
            nextPageUrl: '',
            currentPageNo: '',
            prevPageUrl: '',
            apiUrl: 'http://127.0.0.1:8000/api/cocktails'
        }
    },

    methods: {
        getCocktails(apiUrl = this.apiUrl){
            axios.get(apiUrl).then((response)=>{
                console.log(response);
                this.cocktailsList = response.data.results.data;
                this.nextPageUrl = response.data.results.next_page_url;
                this.prevPageUrl = response.data.results.prev_page_url;
            })
            .catch(function(error){
                console.log(error);
            })
        },

        nextPage(){
            // alert('next page');
            this.getCocktails(this.nextPageUrl);
        },

        prevPage(){
            // alert('prev page');
            this.getCocktails(this.prevPageUrl);
        }
    },

    created(){
        this.getCocktails();
    }
}
</script>
<style lang="scss" scoped>
    @use '../style/general.scss' as*;

    span{
        cursor: pointer;
    }
    
    h1{
        color:white ;
        font-weight: 900;
    }
</style>