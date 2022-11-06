<script>
    import Person from "../lib/Person.svelte";
    import SubmitButton from "./submitButton.svelte";

    let datares = [];
    let selectorValue;

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

    function fillAll() {
        console.log(selectorValue)
    }

</script>

<div class="container">
    <select class="markSelector" id="fillSelector" bind:value={selectorValue}>
        <option disabled selected value="0" />
        <option value="1" class="selector">Present</option>
        <option value="2" class="selector">Online</option>
        <option value="3" class="selector">Absent</option>
        <option value="5" class="selector">Late</option>
        <option value="4" class="selector">Explained</option>
        <option value="6" class="selector">Sick</option>
        <option value="7" class="selector">Class canceled</option>
    </select>
    
    <button class="fillAllBtn" on:click={fillAll}>Fill All</button>

    <!-- i is used to make sure the correct attendance data is retrieved. i gets incremented for each person -->
    {#each datares as person, i}
        <Person {person} {i} />
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

    .markSelector {
        font-size: 22px;
        margin-bottom: 0.9rem;
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
        box-shadow: 7px 6px 28px 1px rgba(0, 0, 0, 0.25);
        cursor: pointer;
        outline: none;
        transition: 0.2s all;
    }

    .fillAllBtn:active {
        transform: scale(0.95);
        box-shadow: 3px 2px 22px 1px rgba(0, 0, 0, 0.25);
    }
</style>
