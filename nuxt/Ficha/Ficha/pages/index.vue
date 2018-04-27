<template>
    <!-- <header class="main-header">
        <nav class="main-nav">
            <ul class="nav-links">
                <nuxt-link to="/" tag="li" class="nav-link"><a>All Posts</a></nuxt-link>
                <nuxt-link to="/about" tag="li" class="nav-link"><a>About</a></nuxt-link>
            </ul>
        </nav>
    </header> -->
    <div class="app">
        <app-ficha-produto v-for="(artigo, index) in artigos"
                           :key="index"
                           :produto="artigo.produto"
                           :valor="artigo.valor" />
    </div>
</template>

<script>
    import axios from 'axios';
    import appFichaProduto from '@/components/app-ficha-produto/app-ficha-produto';
    export default {
        components:{
            appFichaProduto
        },
        asyncData(){
            return axios.get('https://umaartigos-c50bd.firebaseio.com/.json')
                .then((res) => {
                    return { artigos: res.data }
                })
        },
        // async asyncData(){
        //     let { data } = await axios.get('https://umaartigos-c50bd.firebaseio.com/')
        //     return { artigos: data }
        // },
    }
</script>

<style scoped>
    .app{
        margin-top: 4.5rem;
        display: flex;
        align-items: center;
        flex-direction: column;
    }
    /*
    .main-header{
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        background: #022d30;
        height: 4.5rem;
    }

    .main-nav{
        height: 100%;
    }

    .nav-links{
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
    }

    .nav-link{
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 0.1rem;
        padding: 0.3rem;
    }

    .nav-link a {
        display: block;
        text-decoration: none;
        color: white;
    }

    .nav-link a:hover,
    .nav-link a:active,
    .nav-link.nuxt-link-exact-active a {
        color: #06c4d1;
    } 

    .nav-link.nuxt-link-exact-active {
        border-bottom: 3px solid #06c4d1;
    }
    */
</style>