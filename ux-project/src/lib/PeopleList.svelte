<script>
    import Person from "../lib/Person.svelte";

    // 25 random people fetched from the api, this data is then formatted into json.
    const response = fetch(
        "https://randomuser.me/api/?results=25&nat=GB,NZ,US,AU"
    );
    let datares = [];
    response.then((res) => {
        res.json().then((data) => {
            datares = data.results;
            console.log(data.results);
        });
    });
</script>

<div class="container">
    <!-- i ise used to make sure the correct attendance data is gotten. i gets incremented for each person -->
    {#each datares as person, i}
        <Person {person} {i} />
    {/each}
</div>

<style>
    .container {
        border: solid black 1px;
        padding: 2vw;
        width: 50vw;
        margin: 0 auto;
        min-width: 580px;
    }
</style>
