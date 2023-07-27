<template>
	v-for="post in posts"
</template>

<script setup lang="ts">
defineProps<{ 
	posts: { id: number; title: string; body: string; }[];
}>()
</script>
