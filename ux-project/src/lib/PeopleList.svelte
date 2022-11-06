<script>
    // Imports
    import Person from "../lib/Person.svelte";
    import SubmitButton from "./submitButton.svelte";

    // Variables
    let datares = [];
    let selectedOptions = [];
    let fillAllWith;

    // 25 random people fetched from the api, this data is then formatted into json.
    const response = fetch(
        "https://randomuser.me/api/?results=25&nat=GB,NZ,US,AU"
    );

    response.then((res) => {
        res.json().then((data) => {
            datares = data.results;
            console.log(data.results);
        });
    });

    function fillAll(event) {
        selectedOptions = selectedOptions.fill(fillAllWith);
    }
</script>

<div class="container">
    <div class="fillWrapper">
        <button class="fillAllBtn" on:click={fillAll}>Fill All</button>

        <select class="markSelector" id="fillSelector" bind:value={fillAllWith}>
            <option disabled selected value="0" />
            <option value="1" class="selector">Present</option>
            <option value="2" class="selector">Online</option>
            <option value="3" class="selector">Absent</option>
            <option value="5" class="selector">Late</option>
            <option value="4" class="selector">Explained</option>
            <option value="6" class="selector">Sick</option>
            <option value="7" class="selector">Class cancelled</option>
        </select>
    </div>
    <!-- i is used to make sure the correct attendance data is retrieved. i gets incremented for each person -->
    {#each datares as person, i}
        <Person {person} {i} bind:value={selectedOptions[i]} />
    {/each}
    <SubmitButton />
</div>

<style>
    .container {
        border: solid black 1px;
        padding: 1rem 2vw 1rem 2vw;
        width: 50vw;
        margin: 0 auto;
        min-width: 580px;
        margin-bottom: 2rem;
    }

    .container:after {
        content: "";
        clear: both;
        display: table;
    }

    .fillWrapper {
        overflow: auto;
    }

    .markSelector {
        font-size: 22px;
        margin-bottom: 1rem;
        margin-right: 0.5rem;
        margin-top: 3px;
        float: right;
    }

    .selector {
        font-size: 18px;
    }

    .fillAllBtn {
        text-decoration: none;
        border: none;
        padding: 0.4rem 1rem;
        font-size: 16px;
        background-color: green;
        color: #fff;
        border-radius: 5px;
        cursor: pointer;
        outline: none;
        transition: 0.2s all;
        float: right;
    }

    .fillAllBtn:active {
        transform: scale(0.95);
    }
</style>
