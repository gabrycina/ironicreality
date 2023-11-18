<script lang="ts">
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	export let data;
</script>

<svelte:head>
	<title>Ironic Reality</title>
</svelte:head>

<Header navigation={data.topNavigation} />
<slot />
<Footer />
