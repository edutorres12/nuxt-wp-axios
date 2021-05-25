<template>
  <div class="container">
      <ul>
        <li v-for="blog in blogs" :key="blog.id">
          {{blog.title.rendered}}
          <NuxtLink  :to="`posts/${blog.id}`">
            Ver más
          </NuxtLink>

        </li>
      </ul>
  </div>
</template>

<script>
export default {
async asyncData({ $axios }) {
  const blogs = await $axios.$get('http://localhost/TemplateEnBlancoHeadless/wp-json/wp/v2/posts')
  return { blogs }
}

}

</script>

<style>

</style>
