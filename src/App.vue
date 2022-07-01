<template>
    <post-form  @createPost="createPost"/>
    <posts-list :posts="posts" @delete-post="deletePost"/>
</template>

<script>
	import PostForm from "@/components/PostForm";
	import PostsList from "@/components/PostsList";

	export default {
		components: {PostsList, PostForm},
		data() {
			return {
				posts: [
					{id: 1, title: 'SomeTitle1', body: 'message1'},
					{id: 2, title: 'SomeTitle2', body: 'message2'},
					{id: 3, title: 'SomeTitle3', body: 'message3'},
				]
			}
		},
		methods: {
			createPost(post) {
				console.log(post )
				this.posts.push(post)
			},
			deletePost(id){
				this.posts=this.posts.filter(e=>e.id!==id)
            }
		}
	}
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
</style>