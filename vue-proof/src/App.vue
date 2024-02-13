<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Hello from "./Hello.vue";
import axios from 'axios';

let names = ref([]);
const update_list = async () => {
	const data = (await axios.get("http://localhost:8000/get-users")).data;
	names.value = data;
}

onMounted(() => {
	update_list()
})

</script>

<template>
	<Hello :names="names" />
</template>
