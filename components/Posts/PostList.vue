<template>
    <div>
        <section class="featured-posts">
            <PostPreview v-for="post in posts" :id="post.id" :key="post.id" :is-admin="isAdmin" :thumbnail="post.thumbnail" :title="post.title" :previewText="post.previewText" />
        </section>
    </div>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview'

export default {
    components: {
        PostPreview
    },
    props: {
        isAdmin: {
            type: Boolean,
            default: false
        },
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>


<style scoped>
.featured-posts {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

.no-class {}
</style>
