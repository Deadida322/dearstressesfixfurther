<template>
    <v-container class="mt-4" v-if="show">
        <v-row no-gutters>
            <v-col class="col col-1"></v-col>
            <v-col class="col col-10">
                <v-row class="pa-2 mb-2">
                    <h1 class="text-h4">Новости</h1>
                </v-row>
            </v-col>
            <v-col>
            </v-col>
        </v-row>
        <v-row no-gutters>
            <v-col class="col col-1"/>
            <v-col class="col col-10">
                  <v-text-field 
                    class="courses__input_search"  
                    placeholder="Поиск новости..."
                    persistent-hint
                    append-icon="mdi-magnify" 
                    dense
                    solo
                >
                </v-text-field>
                <h1 class="text-h5 mb-4">Доступные новости</h1>
                <NewsItem v-for="(newsItem, index) in news" :key="index" :item="newsItem" />
                    
            </v-col>
            <v-col class="col сщд-1">
               
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
import NewsItem from '@/components/news/NewsItem'
export default {
    components: {
        NewsItem
    },
    created(){
        this.time = new Date()
    },
    mounted(){
        
        this.time = new Date() - this.time
        console.log(this.time);
    },
    fetch(){
        this.news = this.$axios.get('/api/v1/news/').then(res=>{
            this.news=res.data.results
            this.show=true
        })
    },
    data(){
        return ({
            show: false,
            news: [],
            time: 0
        })
    },
    
}
</script>



