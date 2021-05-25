<template>
    <div class="container">
        <div class="row">
            <div class="col-lg-12">
                <h2>{{post.title.rendered}}</h2>
            </div>
            <div class="col-lg-12">
                <div class="content" v-html="post.content.rendered"></div>
            </div>
        </div>
        

        
    </div>
</template>

<script>
    export default {
        async asyncData({params, $axios}){
            
            const post = (await $axios.get(`http://localhost/TemplateEnBlancoHeadless/wp-json/wp/v2/posts/${params.id}`)).data
            
            return { 
                post
            }
        }
    }
</script>

<style scoped>
.content >>> img{
        width: 100%;
    }
</style>