<template>
	<div class="heart-container">
		<div @click="showYellowHeart = true">🖤</div>
		<transition>
			<div @click="showYellowHeart = false" v-show="showYellowHeart">💛</div>
		</transition>
	</div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const showYellowHeart = ref<boolean>(false);
</script>

<style scoped>
.heart-container {
	display: grid;
	grid-template: '❤️';
	font-size: 75px;
	place-items: center;
	border: 1px solid black;
	background-color: lightblue;
}

.heart-container > * {
	grid-area: ❤️;
	margin: 1rem;
}

.heart-container > *:first-child {
	border: 1px solid black;
}

.v-enter-from,
.v-leave-to {
	transform: scale(0);
}
.v-enter-to,
.v-leave-from {
	transform: scale(1);
}
.v-leave-active,
.v-enter-active {
	transition: all 1s ease-in-out;
}
</style>
