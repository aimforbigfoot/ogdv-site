<script>
    import { initializeApp } from "firebase/app"
    import { firebaseConfig } from "../FirebaseConfig"
    import { collection, getDocs, getFirestore, query } from "firebase/firestore";
    import { onMount } from "svelte";
    const firebaseApp = initializeApp(firebaseConfig)
    const db = getFirestore(firebaseApp);

    let emailToUse = ""

    onMount( () => {
        console.log("yes")
    } )

    const subBtnPress = async () => {
        console.log("FUCING IBTHC ")
        const q = query(collection(db, "emails") );
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
                console.log(doc.id, " => ", doc.data());
            OKAY PAUSE ARE WE DOING PROFILES OR EMAIL SIGNSUPS !?!?!?
    }




            })

    }

</script>

<div>
    <div class="pa4-l">
        <div class="bg-light-red mw7 center pa4 br2-ns ba b--black-10">
            <section class="cf bn ma0 pa0">
            <div class="pa0 f5 f4-ns mb3 black-80">Sign up for our newsletter</div>
            <div class="cf">
                <label class="clip" for="email-address">Email Address</label>
                <input class="f6 f5-l input-reset bn fl black-80 bg-white pa3 lh-solid w-100 w-75-m w-80-l br2-ns br--left-ns" placeholder="Your Email Address" type="text" name="email-address" bind:value={emailToUse} >
                <button class="f6 f5-l button-reset fl pv3 tc bn bg-animate bg-black-70 hover-bg-black white pointer w-100 w-25-m w-20-l br2-ns br--right-ns" on:click={subBtnPress}>Subscribe</button>
            </div>
            </section>
        </div>
    </div>
</div>