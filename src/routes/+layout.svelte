<script lang="ts">
  import "../app.css";
	import Header from '$lib/components/Header.svelte'
  import Footer from '$lib/components/Footer.svelte'

  export let data;
</script>

<Header navigation={data.topNavigation}/>
  <slot />
<Footer />