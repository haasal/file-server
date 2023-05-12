<script lang="ts">
	import { onMount } from 'svelte';
	let msg = '';

	onMount(async () => {
		msg = await (await fetch('/api/hello')).text();
		console.log(msg);
	});
</script>

<h1>Welcome to File Server</h1>
<h2>
	{msg}
</h2>
