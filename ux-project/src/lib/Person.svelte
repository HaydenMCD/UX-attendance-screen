<script>

</script>

<div class="personWrapper"> 
    <img src="https://play-lh.googleusercontent.com/IeNJWoKYx1waOhfWF6TiuSiWBLfqLb18lmZYXSgsH1fvb8v1IYiZr5aYWe0Gxu-pVZX3" alt="The rock" class="profilePic">
    <p class="lastName">Last name</p>
    <p class="firstName">First name</p>
    <select class="markSelector">
        <option disabled selected value="0"></option>
        <option value="1">Present</option>
        <option value="2">Online</option>
        <option value="3">Absent</option>
        <option value="5">Late</option>
        <option value="4">Explained</option>
        <option value="6">Sick</option>
        <option value="7">Class canceled</option>
    </select>
</div>

<style>
.personWrapper{
    display: flex;
    background-color: #d1d1d1;
    margin-bottom: 10px;
}

.profilePic{
    max-width: 3.5rem;
    max-height: 3.5rem;
    border-radius: 50%;
}

.firstName{
    margin-left: .5vw;
}

.lastName{
    margin-left: 3rem;
}

.markSelector {
    margin-top: 17px;
    max-height: 3vh;
    max-width: 10vw;
    margin-left: 1rem;
    width: 20vw;
}
</style>