<template>
    <div class="admin-new-post">
        <section class="new-post-form">
            <AdminPostForm @submit="onSubmitted" />
        </section>
    </div>
</template>

<script>
import axios from 'axios'
import AdminPostForm from '@/components/Admin/AdminPostForm'

export default {
    layout: 'admin',
    components: {
        AdminPostForm
    },
    methods: {
        onSubmitted(postData) {
            this.$store.dispatch('addPost', postData)
                .then(() => {
                    this.$router.push('/admin');
                })       
        }
    }
}
</script>
