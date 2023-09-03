<script>
  import AboutUs from "../comps/AboutUs.svelte";
    import EmailSignUp from "../comps/EmailSignUp.svelte";
  import EventInfo from "../comps/EventInfo.svelte";
  import IntroPage from "../comps/IntroPage.svelte";
    import RedAndWhiteBar from "../comps/RedAndWhiteBar.svelte";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<main class="w-100-l rainbow-box">
  <RedAndWhiteBar />
  <IntroPage />
  <hr>
  <AboutUs />
  <hr>
  <EventInfo />
  <hr>
  <EmailSignUp />
  <hr>
</main>
