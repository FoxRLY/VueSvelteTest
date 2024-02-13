<script lang="ts">
	import axios from 'axios';
	import Hello from './Hello.svelte';
	import { onMount } from 'svelte';

	let names: string[] = [];

	const update_list = async () => {
		let data = (await axios.get('http://localhost:8000/get-users')).data;
		names = data.map((entry) => entry.name);
	};

	onMount(() => {
		update_list();
	});
</script>

<Hello {names} />
