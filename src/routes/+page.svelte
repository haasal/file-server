<script lang="ts">
	async function fetchApi() {
		return await (await fetch('/api/hello')).text();
	}

	let msg: Promise<String>

	function handleClick() {
		msg = fetchApi()
	}
</script>

<h1>Welcome to File Server</h1>
<button on:click={handleClick}>
	{#await msg}
		...waiting
	{:then text}
		{#if text}
			{text}
		{:else}
			Click me!
		{/if}
	{/await}
</button>
