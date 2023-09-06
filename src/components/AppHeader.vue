<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <ul class="navbar-nav mr-auto">
                    <li class="nav-item active" v-for="link in links">
                        <router-link :to="{name: link.route}">
                            {{ link.name }}
                        </router-link>
                    </li>
                </ul>
        </nav>
    </header>
</template>
<script>
export default {
    name:'AppHeader',

    data(){
        return{
            links : [
                {
                    route: 'cocktails',
                    name: 'Cocktails'
                },
                {
                    route: 'aboutUs',
                    name: 'About Us'
                },
                {
                    route: 'contacts',
                    name: 'Contacts'
                }
            ]
        }
    },
    
}
</script>
<style lang="scss">

    nav.navbar{
        padding: 3rem;

        ul{
            width: 100%;
            list-style-type: none;

            li{
                margin: 0 auto;

                a{
                    color: black;
                    text-decoration: none;
                    font-size: 2rem;
                }
            }
        }
    }
</style>