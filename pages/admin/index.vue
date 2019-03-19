<template>
    <div class="admin-page">
        <section class="new-post">
            <AppButton @click="$router.push('/admin/new-post')">Create Post</AppButton>
        </section>
        <section class="existing-posts">
            <h1>Existing Posts</h1>
            <PostList :posts="loadedPosts" isAdmin  />
        </section>
    </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'
import AppButton from '@/components/UI/AppButton'

export default {
  layout: 'admin',
  components: {
        PostList,
        AppButton
  },
  computed: {
    loadedPosts() {
      return this.$store.getters.loadedPosts
    }
  },
  // asyncData(context, callback) {
  //   setTimeout(() => {
  //     callback(null, {
  //       loadedPosts: [{
  //         id: '1', 
  //         title: 'First Post',
  //         previewText: 'This is our first post!',
  //         thumbnail: 'http://jolttx.com/wp-content/uploads/2019/02/technology-16-9.jpg'
  //       }, {
  //         id: '2', 
  //         title: 'Second Post',
  //         previewText: 'This is our second post!',
  //         thumbnail: 'http://jolttx.com/wp-content/uploads/2019/02/technology-16-9.jpg'
  //       }]
  //     })
  //   }, 1500)
  // }    
}
</script>

<style scoped>
.admin-page {
  padding: 20px;
}

.new-post {
  text-align: center;
  border-bottom: 2px solid #ccc;
  padding-bottom: 10px;
}

.existing-posts h1 {
  text-align: center;
}
</style>

