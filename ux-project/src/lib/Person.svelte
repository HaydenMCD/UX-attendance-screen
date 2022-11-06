<script>
    export let person;
    export let i;
    import AttendanceHistory from "./attendanceHistory.svelte";
</script>

<div class="personWrapper">
    <div class="picwrapper">
        <a href="/"><img src={person.picture.thumbnail} alt="The rock" class="profilePic" /></a>
    </div>
    <div class="namewrapper">
        <h1><a href="/" class="nameLink">{person.name.first} {person.name.last}</a></h1>
    </div>

    <!-- displays the attendance history for a given person -->
    <AttendanceHistory {i}/>

    <select class="markSelector" id="selector" required>
        <option disabled selected value="0" />
        <option value="1" class="selector">Present</option>
        <option value="2" class="selector">Online</option>
        <option value="3" class="selector">Absent</option>
        <option value="5" class="selector">Late</option>
        <option value="4" class="selector">Explained</option>
        <option value="6" class="selector">Sick</option>
        <option value="7" class="selector">Class canceled</option>
    </select>
</div>

<style>
    .personWrapper {
        display: flex;
        justify-content: space-around;
        background-color: #d1d1d1;
        margin-bottom: 10px;
        align-items: center;
        padding-left: 1rem;
        padding-right: 1rem;
    }

    .namewrapper {
        display: flex;
        flex: 1.5;
        align-self: center;
    }

    .picwrapper {
        flex: 1;
    }

    .profilePic {
        max-width: 3.5rem;
        max-height: 3.5rem;
        border-radius: 50%;
    }

    .markSelector {
        font-size: 22px;
    }

    .selector {
        font-size: 18px;
    }

    h1 {
        font-size: 20px;
        line-height: 24px;
        font-weight: 400;
    }

    .nameLink {
        text-decoration: none;
        color: blue;
    }
</style>