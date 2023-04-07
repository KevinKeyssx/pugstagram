<script>
	// !Imports
    import Header 	    from '../components/Header.svelte';
    import Timeline     from '../components/Timeline.svelte';
    import Sidebar      from '../components/Sidebar.svelte';
	import Footer 	    from "../components/Footer.svelte";
    import Main         from '../components/Main.svelte';
    import { onMount }  from 'svelte';

    let data = {};
    const API  = 'https://kittygram-api.now.sh/';

    onMount(async () => {
        const response = await fetch( API );
        data = await response.json();

		console.log('***DATA*** ~', data);
    });

</script>

<style>

	@import url(https://fonts.googleapis.com/css?family=Lato:300,400&display=swap);
	@import url(https://fonts.googleapis.com/css?family=Pacifico:swap);

	:global(body) {
        background-color    : #fafafa;
        color               : rgba(38, 38, 38, 0.7);
        font-family         : "Lato",sans-serif;
        margin              : 0;
        padding             : 0;
    }

	:global(h1, h2, h3) {
		margin              : 0;
        padding             : 0;
	}

</style>

<Header />

<Main>
    <Timeline posts={data.posts} />
    <Sidebar {...data.user}/>

</Main>
<Footer />
