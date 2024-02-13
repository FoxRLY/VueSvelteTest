<script setup lang="ts">

defineProps([
	"names"
]);

</script>

<template>
	<div v-for="name in names">
		<p>Hello {{name.name}}</p>
	</div>
</template>
