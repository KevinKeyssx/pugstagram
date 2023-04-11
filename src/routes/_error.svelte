<script>
	import Main from "../components/Main.svelte";

	export let status;
	export let error;

	const dev = process.env.NODE_ENV === "development";
</script>

<svelte:head>
	<title>{ status }</title>
</svelte:head>

<style>
	.Error {
		padding: 4em 0 0 0;
	}

	h1, p {
		margin: 0 auto;
		text-align: center;

	}

	h1 {
		font-size: 2.8em;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

</style>


<Main>

	<div class='Error'>
		<h1>{ status }</h1>
		<p>{ error.message }</p>

		<img
			src="https://res.cloudinary.com/dbgzsikcs/image/upload/v1681179540/instapetsgram/404_fbqdh0.png"
			alt="Page not found"
			width="100%"
		>

		{#if dev && error.stack}
			<pre>{ error.stack }</pre>
		{/if}

	</div>

</Main>
