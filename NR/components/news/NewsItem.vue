<template>
    <v-card class="mt-3">
        
        <v-row no-gutters>       
             <v-col class="col col-3">
                <v-avatar
                    tile
                    class="ma-4"
                    size="200"
                    color="grey"
                >
                    <v-img 
                        :src="item.image"
                    >

                    </v-img>
                </v-avatar>
            </v-col>
            <v-col class="d-flex flex-column justify-space-between col col-9">
                <div class="">
                    <v-card-title>
                    {{item.title}}
                </v-card-title>
                <v-card-subtitle>
                    {{item.date}}
                </v-card-subtitle>
                <v-card-text>
                    {{item.description}}     
                </v-card-text>
                </div>
                
                 <v-card-actions>
                    <v-chip-group
                        active-class="deep-purple--text text--accent-4"
                        mandatory
                    >
                        <v-chip nuxt :to="`/tags/${tag}`" v-for="(tag, id) in item.tags" :key="id">{{tag.name}}</v-chip>
                    </v-chip-group>
                        <v-spacer>

                        </v-spacer>
                        <v-btn
                            nuxt
                            :to="`/news/${item.id}`"
                            color="primary lighten-2"
                            text
                            small
                        >
                            подробнее
                        </v-btn>
                            
                </v-card-actions>
            </v-col>           
        </v-row>
        
    </v-card>
</template>


<script>
export default {
    props:{
        item: {
            type: Object,
            required: true
        }
    }
}
</script>



