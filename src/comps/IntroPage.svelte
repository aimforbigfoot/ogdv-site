<script>
    import { scrollTo } from 'svelte-scrolling';
    import logo from '../lib/images/logo.png';
</script>

<div class="flex justify-center">
    <div
        class="flex flex-column flex-row-ns justify-between items-center w-90-ns mw7-l mt5 landing-title mr4 pr4"
    >
        <div class="mr4">
            <div
                class="ml2 mr2 b tc br b--white border w-100-l flex flex-column justify-around h-100"
            >
                <a class="pv3 mv3 f3" use:scrollTo={'about'}>ABOUT US </a>
                <a class="pv3 mv3 f3" use:scrollTo={'eventInfo'}>EVENT INFO</a>
                <a class=" mv3 f3" use:scrollTo={'signUp'}>SIGN UP</a>
            </div>
        </div>
        <div class="mw5">
            <img src={logo} alt="logo" class="logo-image" />
        </div>
        <div
            class=" tl di pl4 title white white-text-with-red-shadow pulsating-shadow"
        >
            <h1 class="di tl f3 pa0 ma0">ONTARIO</h1>
            <br />
            <h1 class="di tl i f1 pa0 ma0">GAMEVERSE</h1>
        <br />
            <h1 class="tl bigBlitzText">BLITZ</h1>
        </div>
    </div>
</div>
