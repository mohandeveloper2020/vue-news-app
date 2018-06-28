<template>
    <div class="grid-container">
        <ul class="news-list">
            <li v-for="post in posts">
                <h5>{{ post.source.name }}</h5>
                <h3><a :href="post.url" target="_blank">{{ post.title }}</a></h3>
                <img :src="post.urlToImage" alt="urlToImage" />
                <p>{{ post.description }}</p>
                <h5 class="news-list_author">Author: {{ post.author }}</h5>
                <button><a :href="post.url">Know more</a></button>
            </li>
        </ul>        
    </div>
</template>

<script>

    import axios from 'axios';

    export default {
        name: 'NewsList',

        data() {
            return {
                posts: []
            }
        },

        created(){        
            axios.get('https://newsapi.org/v2/everything?q=apple&from=2018-06-20&to=2018-06-20&sortBy=popularity&apiKey=6c13a32e23b643989e19a722674ca873')
                .then(posts => {
                    console.log(posts.data.articles);
                    this.posts = posts.data.articles;
            })
        }             
    }

    export default {
        name: 'NewsList',

        data() {
            return {
                posts: []
            }
        },

        created(){        
            axios.get('https://newsapi.org/v2/everything?q=apple&from=2018-06-20&to=2018-06-20&sortBy=popularity&apiKey=6c13a32e23b643989e19a722674ca873')
                .then(posts => {
                    console.log(posts.data.articles);
                    this.posts = posts.data.articles;
            })
        }             
    }
</script>

<style scoped>
    .grid-container {
        margin: 0 auto;
        width: 100%;
    }

    .news-list {
        list-style-type: none;
        padding: 0;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }

    @media(max-width: 1023px){
        .news-list {
            grid-template-columns: repeat(2, 1fr);
        }
    }

    @media(max-width: 767px){
        .news-list {
            grid-template-columns: 1fr;
        }
    }

    .news-list li {
        border-bottom: 1px solid #ccc;
        padding: 0 20px;
        margin: 20px;
        text-align: left;
        box-shadow: 0 2px 2px rgba(0,0,0,.1);
    }

    .news-list li:hover {
        transform: translate3D(0,-2px,0) scale(1);
        box-shadow: 0 15px 50px rgba(0,0,0,.2);
    }

    .news-list li h3 a{
        color: #FF5733;
        text-decoration: none;
    }

    .news-list li h3 a:hover{
        color: #3498DB;
        text-decoration: underline;
    }

    .news-list .news-list_author{
        font-style: italic;
        color: #999;
        font-weight: normal;
        margin: 0;
    }

    img {
        width: 80%;
    }

    button {
        padding: 10px;
        border: none;
        background: #FF5733;
        margin: 10px 0;
    }

    button:hover {
        background: #3498DB;
    }

    button a {
        text-decoration: none;
        color: #fff;
    }

</style>