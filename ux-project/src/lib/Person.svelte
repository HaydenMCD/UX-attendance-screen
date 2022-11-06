<script>
    export let person;
    export let i;
    import AttendanceHistory from "./attendanceHistory.svelte";
    import Modal from "svelte-simple-modal";
    import Content from "./content.svelte";
</script>

<div class="personWrapper">
    <Modal>
        <Content {person} />
    </Modal>

    <!-- displays the attendance history for a given person -->
    <AttendanceHistory {i} />

    <select class="markSelector" id="selector" required>
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

    .markSelector {
        font-size: 22px;
    }

    .selector {
        font-size: 18px;
    }
</style>
