<script setup>
	import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
	<div class="wrapper-content">
		<div class="app">
			<router-view />
		</div>
	</div>
</template>

<style scoped>
	.app {
		font-family: 'Roboto', Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-align: center;
		max-width: 1060px;
		margin: auto;
		overflow-x: hidden;
	}
	.wrapper-content {
		width: 100vw;
		background-color: #ccb6a8;
		overflow-x: hidden;
	}
</style>
