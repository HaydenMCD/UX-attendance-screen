<script>
    // This function would submit the attendance data a database. For testing purposes i refresh the page when clicked
    function submit() {
        location.reload();
        console.log("clicked")
    }
</script>

<button class="submitBtn" on:click={submit}>Submit attendance</button>

<style>
.submitBtn {
    text-decoration: none;
    border: none;
    padding: .6rem 2rem;
    margin-top: 1rem;
    font-size: 16px;
    background-color: green;
    color: #fff;
    border-radius: 5px;
    box-shadow: 7px 6px 28px 1px rgba(0, 0, 0, 0.25);
    cursor: pointer;
    outline: none;
    transition: 0.2s all;
    float: right;
}

/* when the button is clicked the size will go smaller and the shadow will be lowered */
.submitBtn:active {
    transform: scale(0.95);
    box-shadow: 3px 2px 22px 1px rgba(0, 0, 0, 0.25);
}
</style>