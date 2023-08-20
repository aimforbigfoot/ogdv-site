<script>
    import AboutUs from "../comps/AboutUs.svelte";
import EventInfo from "../comps/EventInfo.svelte";
import IntroPage from "../comps/IntroPage.svelte";

</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>


<main class="ml-auto mr-auto w-80">
	<IntroPage />
	<EventInfo />
	<AboutUs />
	<p> HELLO I AM ALIVE </p>
	
	<div class="rainbow-box">
		helol
	</div>
</main>