<script>
   import Person from "../lib/Person.svelte";
   import {HISTORY} from '../assets/attendanceData'


        const response = fetch("https://randomuser.me/api/?results=25&nat=GB,NZ,US,AU");
        let datares = [];
        response.then(res => {
            res.json().then(data => {
                datares = data.results
                console.log(data.results)
            })
        });

</script>
  
<div class="container">

    {#each datares as person, index}
        <Person person={person} />
    {/each}

</div>

<style>
.container{
border: solid black 1px;
padding: 2vw;
width: 50vw;
margin: 0 auto;
min-width: 580px;
}

</style>