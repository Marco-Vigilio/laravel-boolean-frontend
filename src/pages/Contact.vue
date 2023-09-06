<template>
    
        <h1 class="text-center">Contact Us!</h1>

        <form class="col-8 mx-auto">
            <div class="mb-3">
                <label for="exampleInputEmail1" class="form-label" ></label>
                <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp" placeholder="Email address...">
                <div id="emailHelp" class="form-text"></div>
            </div>

            <div class="mb-3">
                <label for="exampleInputPassword1" class="form-label"></label>
                <textarea class="form-control" id="exampleInputPassword1" rows="8" placeholder="Text..."></textarea>
            </div>

            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    
</template>
<script>
export default {
    
}
</script>
<style lang="scss" scoped>
    @use '../style/general.scss' as*;
    
    h1{
        color:white ;
        font-weight: 900;
    }

</style>