<script>
    import { initializeApp } from 'firebase/app';
    import { firebaseConfig } from '../FirebaseConfig';
    import {
        collection,
        doc,
        getDocs,
        getFirestore,
        query,
        setDoc,
    } from 'firebase/firestore';
    import { onMount } from 'svelte';
    const firebaseApp = initializeApp(firebaseConfig);
    const db = getFirestore(firebaseApp);
    import { v4 as uuidv4 } from 'uuid';

    let userEmail = '';
    let signedUpSuccessfully = false;
    let showWarningError = false;

    onMount(() => {
        console.log('yes');
    });

    function isValidEmail(email) {
        const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
        return regex.test(email);
    }

    const subBtnPress = async () => {
        console.log('YES I GOT A CLICK');
        if (isValidEmail(userEmail)) {
            showWarningError = false;
            signedUpSuccessfully = true;
            const ref = collection(db, 'emails');
            await setDoc(doc(ref, uuidv4()), {
                userEmail,
            });
        } else {
            showWarningError = true;
        }
    };

    const handleInputForEmailSub = (e) => {
        showWarningError = false
        if (e.code == 'Enter') {
            subBtnPress();
        }
    };
</script>

<div>
    <div class="pa4-l pb4 mb7">
        <div class="bg-white mw7 center pa4 br2-ns ba b--black-10">
            <section class="cf bn ma0 pa0">
                {#if !signedUpSuccessfully}
                    <h1 class="pa0 f1 tc fw7 ma0 pa0 mb3 black-80">
                        Sign up for our newsletter
                    </h1>
                    <div class="cf">
                        <label class="clip" for="email-address"
                            >Email Address</label
                        >
                        <input
                            on:keyup={(e) => handleInputForEmailSub(e)}
                            class="f6 f5-l input-reset bn fl black-80 bg-white pa3 lh-solid w-100 w-75-m w-80-l br2-ns br--left-ns"
                            placeholder="Your Email Address"
                            type="text"
                            name="email-address"
                            bind:value={userEmail}
                        />
                        <button
                            class="f6 f5-l button-reset fl pv3 tc bn bg-animate bg-black-70 hover-bg-black white pointer w-100 w-25-m w-20-l br2-ns br--right-ns"
                            on:click={subBtnPress}>Subscribe</button
                        >
                    </div>
                {/if}
                {#if signedUpSuccessfully}
                    <div class="tc">
                        <h1 class="fw9 f1">Thank you for signing up</h1>
                        <p class="f3">Stay tuned for event related emails</p>
                    </div>
                {/if}
            </section>
            {#if showWarningError}
                <div class="bg-black br-pill red tc pa3 f2 mt3">
                    ERROR: INVALID EMAIL
                </div>
            {/if}
        </div>
    </div>
</div>
