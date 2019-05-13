<template>
  <section class="container">
  <h2>{{title}}</h2>
  <p>{{currentArticles.title}} </p>
  <ul>
    <li v-for="article in articles" :key="article.id">
        {{ article.title }}</li>
    </ul>
  </section>
</template>
<script>
export default{

    data(){
        return{
            currentArticles: null,
            //title: "Mes articles",
            articles: [
                {id: 1, title: 'Articles1', content: '...'},
                {id: 2, title: 'Articles2', content: '...'},
                {id: 3, title: 'Articles3', content: '...'},
                {id: 4, title: 'Articles4', content: '...'},
            ]
        }
    },
    mounted(){

        this.currentArticles = this.articles.find(item => item.id === this.$route.params.id);
    }
}
</script>