<template>
    <div><strong>Название поста</strong>{{post.title}}</div>
    <div><strong>Описание поста</strong>{{post.body}}</div>
    <my-button @click="deletePost">Delete</my-button>
</template>

<script>
		export default {
			data() {
			return {}
		},
		props: {
			post:
				{type: Object, required: true}
		},
      methods:{
			deletePost(){
				this.$emit('delete-post',this.post.id)
            }
      }
	}
</script>

<style scoped>

</style>