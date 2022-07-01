<template>
    <div v-if="posts.length>0">
        <post-item
                @delete-post='deletePost'
                :post='post'
                :key="post.id"
                v-for="post in posts"/>
    </div>
    <div v-else="posts.length<=0">нет записей</div>
</template>

<script>
	import PostItem from "@/components/PostItem";

	export default {
		components: {PostItem},
		props: {
			posts: {
				type: Array,
				required: true
			}
		},
		methods: {
			deletePost(id) {
				this.$emit('delete-post',id)
			}
		}
	}
</script>

<style scoped>

</style>