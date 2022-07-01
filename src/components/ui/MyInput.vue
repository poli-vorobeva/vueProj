<template>
    <input @input="updateInput"
           :type='type'
           :placeholder='text'
           :value="modelValue">
</template>

<script>
	export default {
		name: 'my-input',
		props: {
			modelValue: [String, Number],
			type: {type: String, required: true},
			text: {type: String, required: true}
		},
		methods: {
			updateInput(e) {
				this.$emit('update:modelValue', e.target.value)
			}
		}
	}
</script>

<style scoped>

</style>