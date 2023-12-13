<script>
	let value = 'fror';

	$: setInterval(async () => {
		try {
			const response = await fetch('/text', {cache: 'no-cache'});
			const data = await response.text();
			value = data;
			console.log('New text loaded', data);
		} catch {
			console.error('Failed to load new text');
		}
	}, 10000);
</script>

<svelte:head>
	<title>@v@</title>
</svelte:head>

<h1>{value}</h1>

<style>
  h1 {
		--text-color: #6d6d6d; /* #ffa500 */
		--text-color-shade: #868584;
		--text-color-constrast: #3e3e3e;
	  color: #fff;
	  margin: auto;
	  font-family: Minecraft, sans-serif;
		font-size: 8rem;
		text-shadow: 0 0 5px var(--text-color), 0 0 15px var(--text-color), 0 0 20px var(--text-color), 0 0 40px var(--text-color), 0 0 60px var(--text-color-constrast), 0 0 10px var(--text-color-shade), 0 0 98px var(--text-color-constrast);
  }
</style>
