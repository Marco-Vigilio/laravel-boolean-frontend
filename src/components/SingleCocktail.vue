<template>
    
    <div class="card">
        <div class="img-wrapper">
            <img  :src="image" alt="">
        </div>
        
        <div class="card-title">
            {{ title }}
        </div>
        <div class="card-content">
            {{ content.substring(0,200) }}
        </div>

    </div>
   
</template>
<script>
export default {
    name:'SingleCocktail',
    data() {
        return {
            
        }
    },
    props:{
        image: String,
        title: String,
        content: String
    }
}
</script>
<style lang="scss" scoped>
    @use '../style/general.scss' as *;
    
    div.card{
        width: calc(( 100% / 4 ) - 30px);
        background-color: gainsboro;
        margin-top: 20px;
        display: flex;
        flex-direction: column;
        align-content: space-between;
        text-align: justify;
        border-radius: 10px;
        padding: 10px 10px;
        &:hover{
            filter: brightness(130%);
            transition: linear .2s;
        }
        

        div.card-title{
            color: black;
            padding: 10px 0px;
            font-size: 1.2rem;
            font-weight: 600;
            text-align: center;
        }

        div.img-wrapper{
            
            border-radius: 10px;
            

            img{
                width: 100%;
                height: 100%;
                object-fit: cover;
                border-radius: 10px;
            }
        }
    }
</style>