<script>
  import { scrollRef, scrollTo } from "svelte-scrolling";
  import Faq from "../comps/Faq.svelte";
  import AboutUs from "../comps/AboutUs.svelte";
  import EmailSignUp from "../comps/EmailSignUp.svelte";
  import EventInfo from "../comps/EventInfo.svelte";
  import IntroPage from "../comps/IntroPage.svelte";
  import SiteFooter from "../comps/SiteFooter.svelte";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<main class="w-full lg:w-100 rainbow-box">
  <IntroPage />
  <div use:scrollRef={"about"}>
    <AboutUs />
  </div>
  <!--
  <div class="eventInfoDiv" use:scrollRef={"eventInfo"}>
    <EventInfo />
  </div>
  -->
  <div class="signUP" use:scrollRef={"signUp"}>
    <EmailSignUp />
  </div>

  <hr />
</main>
<SiteFooter />

<style>
  .title {
    flex-grow: 1;
  }
  .logo-image {
    flex-grow: 1;
  }
  .navbar {
    flex-grow: 1;
  }
</style>
