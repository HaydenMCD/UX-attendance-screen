<script>
import { HISTORY } from "../assets/attendanceData";
export let i
// let session1 = [];
// let session2 = [];

// let currentHistory = HISTORY[i].history

// for (var x = 0; x <= currentHistory.length; x+2) {

// }

// for (var x = 0; x <= currentHistory.length; x + 2) {
//     session1.push(HISTORY[i].history[x])
// }

// console.log(session1)

let historyArray = HISTORY[i].history;
let test = "|";
historyArray.forEach(element => {
    test = test + " " + element + " |"
});


</script>

<p class="history">
    {test}
</p>

<style>
.history {
    display: flex;
    flex: 2;
    font-size: 18px;
}
</style>