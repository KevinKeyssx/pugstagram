<script context="module">
	export async function preload() {
		const response = await this.fetch('https://kittygram-api.now.sh/');
		let data = await response.json();

		return { data };
	}
</script>

<script>
	// !Imports
    import Timeline     from '../components/Timeline.svelte';
    import Sidebar      from '../components/Sidebar.svelte';
	import Footer 	    from "../components/Footer.svelte";
    import Main         from '../components/Main.svelte';


	export let data;
</script>


<svelte:head>
	<title>Instapetsgram</title>
</svelte:head>


<Main>

	<Timeline posts={data.posts} />
    <Sidebar {...data.user}/>

</Main>

<Footer />
