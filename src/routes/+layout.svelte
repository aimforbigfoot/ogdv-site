<script>
  import SiteFooter from "../comps/SiteFooter.svelte";
import "../css/styles.css";
  import "../css/tachyons.css";
</script>

<div class="app bg-black">
  <main>
    <slot />
  </main>
  <SiteFooter />

</div>
