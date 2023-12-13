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
	  color: #fff;
	  margin: auto;
	  font-family: Minecraft, sans-serif;
  }
</style>
