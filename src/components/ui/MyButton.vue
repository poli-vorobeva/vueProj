<template>
   <button class="btn">
      <slot></slot>
   </button>
</template>

<script>
	export default {
name:'my-button'
	}
</script>

<style scoped>
.btn{
   background-color: darkslategray;
   color:wheat;
}
</style>