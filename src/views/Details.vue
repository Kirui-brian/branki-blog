<template>
    <div v-if="error">{{ error }}</div>
    <div v-if="post" class="post">
      <h3>{{ post.title }}</h3>
      <p class="pre">{{ post.body }}</p>
    </div>
</template>
<script>
import getPost from '../composables/getPost'

export default {
  props: ['id'],
  setup(props) {
    getPost(props.id)
      const { post, error, load } = getPost(props.id)

      load()

      return { post, error }
  }
}
</script>

<style>
.post {
  max-width: 2000px;
  margin: 0 auto;
}
.post p {
  color: rgb(138, 17, 74);
  line-height: 1.5em;
  margin-top: 40px;
}
.pre {
  white-space: pre-wrap;
}
</style>