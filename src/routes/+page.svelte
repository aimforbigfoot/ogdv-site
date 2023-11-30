<script>
  import { scrollRef, scrollTo } from "svelte-scrolling";
  import Faq from "../comps/Faq.svelte";
  import AboutUs from "../comps/AboutUs.svelte";
  import EmailSignUp from "../comps/EmailSignUp.svelte";
  import EventInfo from "../comps/EventInfo.svelte";
  import SiteFooter from "../comps/SiteFooter.svelte";
  import * as Accordion from "$lib/components/ui/accordion";
  import * as Sheet from "$lib/components/ui/sheet";
  import { Button } from "$lib/components/ui/button";
  import { Input } from "$lib/components/ui/input";
  import { Label } from "$lib/components/ui/label";
</script>

<svelte:head>
  <title>Home</title>
  <meta name="description" content="Svelte demo app" />
</svelte:head>
<header class="flex justify-between items-center h-12">
  <div class="text-white">logoimg</div>
  <div class="md:flex gap-4 hidden">
    <a href="">FAQ</a>
    <a href="">VOULENTEER</a>
    <a href="">SPONSORS</a>
    <a href="">BE A SPONSOR</a>
    <a href="" class="pr-4">ABOUT US</a>
  </div>
  <div class=" md:hidden inline">
    <Sheet.Root>
      <Sheet.Trigger asChild let:builder>
        <Button builders={[builder]} variant="outline">Open</Button>
      </Sheet.Trigger>
      <Sheet.Content side="right">
        <Sheet.Header>
          <Sheet.Title>Edit profile</Sheet.Title>
          <Sheet.Description>
            Make changes to your profile here. Click save when you're done.
          </Sheet.Description>
        </Sheet.Header>
        <div class="grid gap-4 py-4">
          <div class="grid grid-cols-4 items-center gap-4">
            <Label for="name" class="text-right">Name</Label>
            <Input id="name" value="Pedro Duarte" class="col-span-3" />
          </div>
          <div class="grid grid-cols-4 items-center gap-4">
            <Label for="username" class="text-right">Username</Label>
            <Input id="username" value="@peduarte" class="col-span-3" />
          </div>
        </div>
        <Sheet.Footer>
          <Sheet.Close asChild let:builder>
            <Button builders={[builder]} type="submit">Save changes</Button>
          </Sheet.Close>
        </Sheet.Footer>
      </Sheet.Content>
    </Sheet.Root>
  </div>
</header>
<main class="w-full lg:w-100 flex rainbow-box">
  <div class="red-and-white-bar w-6 bg-red-500 h-screen static"></div>
  <div class="MAIN-SECTION flex flex-col items-center justify-around flex-1">
    <div
      class="flex flex-col items-center justify-center mt-5 md:mt-0 landing-title mr-4"
    >
      <img src={"img/logo.png"} alt="logo" class="max-w-xl" />
      <h2 class="text-white text-center text-4xl">Onatrio's First Jamathon</h2>
    </div>
    <div>
      <div class="ff7 my-20 p-4 max-w-6xl">
        <h2 class="text-4xl">ABOUT US</h2>
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s, when an unknown printer took a galley of type and
          scrambled it to make a type specimen book. It has survived not only
          five centuries, but also the leap into electronic typesetting,
          remaining essentially unchanged.
        </p>
      </div>
      <div>reps from box</div>
      <div class="ff7 w-full p-5">
        <h2>FREQUENTLY ASKED QUESTIONS:</h2>
        <Accordion.Root class="w-full sm:max-w-[70%]">
          <Accordion.Item value="item-1">
            <Accordion.Trigger>Dropdown 1</Accordion.Trigger>
            <Accordion.Content>
              Yes. It adheres to the WAI-ARIA design pattern.
            </Accordion.Content>
          </Accordion.Item>
          <Accordion.Item value="item-2">
            <Accordion.Trigger>Dropdown 2</Accordion.Trigger>
            <Accordion.Content>
              Yes. It comes with default styles that matches the other
              components' aesthetic.
            </Accordion.Content>
          </Accordion.Item>
          <Accordion.Item value="item-3">
            <Accordion.Trigger>Dropdown 3</Accordion.Trigger>
            <Accordion.Content>
              Yes. It's animated by default, but you can disable it if you
              prefer.
            </Accordion.Content>
          </Accordion.Item>
        </Accordion.Root>
      </div>
      <div>reach out/sponsor package</div>
    </div>
  </div>
</main>
