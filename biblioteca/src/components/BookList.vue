<script setup>
import { defineProps } from 'vue'
import Book from './Book.vue'

defineProps({
	books: {
		type: Object,
		required: true,
	},
})
</script>

<template>
	<ul class="grid grid-cols-3 gap-4 place-items-center mx-5 mt-5">
		<Book
			v-for="book in books"
			:key="book"
			:book="book"
			@submit="$emit('buy', $event)"
		/>
	</ul>
</template>
