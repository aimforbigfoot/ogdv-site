<script>
  import { scrollTo } from "svelte-scrolling";
  import logo from "../lib/images/logo.png";
</script>

<div class="flex justify-center">
  <div
    class="flex flex-col md:flex-row justify-between items-center w-90 md:w-full lg:max-w-screen-lg mt-5 md:mt-0 landing-title mr-4 md:pr-4"
  >
    <div class="mr-4">
      <div
        class="ml2 mr2 b tc br b--white border w-100-l flex flex-row lg:flex-col justify-around h-100"
      >
        <a class="pv3 mv3 f3" use:scrollTo={"about"}>ABOUT US </a>
        <a class="pv3 mv3 f3" use:scrollTo={"eventInfo"}>EVENT INFO</a>
        <a class=" mv3 f3" use:scrollTo={"signUp"}>SIGN UP</a>
      </div>
    </div>
    <div class="max-w-5xl">
      <img src={logo} alt="logo" class="logo-image" />
    </div>
    <div
      class="text-left inline-block pl-16 text-4xl text-white pulsating-shadow"
    >
      <h1 class="inline text-left text-3xl p-0 m-0">ONTARIO</h1>
      <br />

      <h1 class="inline text-left italic text-5xl p-0 m-0">GAMEVERSE</h1>
      <br />

      <h1 class="text-left text-9xl font-extrabold tracking-wide bigBlitzText">
        BLITZ
      </h1>
    </div>
  </div>
</div>
