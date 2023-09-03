<script>
    import { initializeApp } from "firebase/app"
    import { firebaseConfig } from "../../FirebaseConfig"
    import { collection, doc, getDocs, getFirestore, query, setDoc } from "firebase/firestore";
    import { onMount } from "svelte";
    const firebaseApp = initializeApp(firebaseConfig)
    const db = getFirestore(firebaseApp);

    $: listOfEmails = []





    onMount( async () => {

        const q = query(collection(db, "emails") );
        const querySnapshot = await getDocs(q);
        querySnapshot.forEach((doc) => {
                console.log(doc.id, " => ", doc.data());
                listOfEmails = [...listOfEmails, doc.data()]
        })



    }) 

</script>

<div>
    TEST
    {#each listOfEmails as email}
        <div>{email.userEmail}</div>
    {/each}
</div>