<template>
    <form @submit.prevent>
        <my-input v-model='post.title'
                  type="text"
                  text="название"/>
        <my-input v-model='post.body'
                  type="text"
                  text="описание"/>
        <my-button @click="addPost">добавить пост</my-button>
    </form>
</template>

<script>
	export default {
		data() {
			return {
				post: {title: '', body: ''}
			}
		},
		methods: {
			addPost() {
				const post = {id: Date.now(), title: this.post.title, body: this.post.body}
				this.post.title='',
                  this.post.body=''
				this.$emit('createPost', post)

			}
		}
	}
</script>

<style scoped>

</style>