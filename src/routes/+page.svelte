<script>
  import { scrollRef, scrollTo } from "svelte-scrolling";
  import Faq from "../comps/Faq.svelte";
  import AboutUs from "../comps/AboutUs.svelte";
  import EmailSignUp from "../comps/EmailSignUp.svelte";
  import EventInfo from "../comps/EventInfo.svelte";
  import SiteFooter from "../comps/SiteFooter.svelte";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>

<main class="w-full lg:w-100 flex rainbow-box">
  <div class="red-and-white-bar w-6 bg-red-500 h-screen"></div>
  <div class="flex justify-around flex-1">
    <div
      class="flex flex-col md:flex-row items-center w-90 md:w-full lg:max-w-screen-lg mt-5 md:mt-0 landing-title mr-4 md:pr-4"
    >
      <div class="max-w-3xl w-1/3">
        <img src={"img/logo.png"} alt="logo" class="logo-image" />
      </div>
      <div
        class="text-left inline-block pl-16 text-4xl text-white pulsating-shadow"
      >
        <h1 class="inline text-left text-3xl p-0 m-0">ONTARIO</h1>
        <br />

        <h1 class="inline text-left italic text-5xl p-0 m-0">GAMEVERSE</h1>
        <br />

        <h1
          class="text-left text-9xl font-extrabold tracking-wide bigBlitzText"
        >
          BLITZ
        </h1>
      </div>
    </div>
  </div>
</main>
