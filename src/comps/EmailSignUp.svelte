<script>
  import { initializeApp } from "firebase/app";
  import { firebaseConfig } from "../FirebaseConfig";
  import {
    collection,
    doc,
    getDocs,
    getFirestore,
    query,
    setDoc,
  } from "firebase/firestore";
  import { onMount } from "svelte";
  const firebaseApp = initializeApp(firebaseConfig);
  const db = getFirestore(firebaseApp);
  import { v4 as uuidv4 } from "uuid";

  let userEmail = "";
  let signedUpSuccessfully = false;
  let showWarningError = false;

  onMount(() => {
    console.log("yes");
  });

  function isValidEmail(email) {
    const regex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    return regex.test(email);
  }

  const subBtnPress = async () => {
    console.log("YES I GOT A CLICK");
    if (isValidEmail(userEmail)) {
      showWarningError = false;
      signedUpSuccessfully = true;
      const ref = collection(db, "emails");
      await setDoc(doc(ref, uuidv4()), {
        userEmail,
      });
    } else {
      showWarningError = true;
    }
  };

  const handleInputForEmailSub = (e) => {
    showWarningError = false;
    if (e.code == "Enter") {
      subBtnPress();
    }
  };
</script>

<div class="mx-auto max-w-screen-xl p-4">
  <div class="pa4-l pb4 mb7">
    <div class="ff7 text-lg mx-auto pt-3 p-4">
      <section class="">
        {#if !signedUpSuccessfully}
          <h1 class="text-5xl text-left font-bold mb-3 text-black-80">
            To stay in touch for important updates:
          </h1>
          <div class="cf">
            <label class="clip" for="email-address">Enter your:</label>
            <input
              on:keyup={(e) => handleInputForEmailSub(e)}
              class=""
              placeholder="email!"
              type="text"
              name="email-address"
              bind:value={userEmail}
            />
            <button class="ff7" on:click={subBtnPress}>[SEND] </button>
          </div>
        {/if}
        {#if signedUpSuccessfully}
          <div class="tc">
            <h1 class="font-extrabold text-left text-9xl">
              Thank you for signing up
            </h1>
            <p class="f3">Stay tuned for event related emails</p>
          </div>
        {/if}
      </section>
      {#if showWarningError}
        <div class="bg-black br-pill red tc pa3 f2 mt3">
          ERROR: Make sure your email is properly formatted.
        </div>
      {/if}
    </div>
  </div>
</div>
