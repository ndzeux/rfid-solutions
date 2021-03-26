<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Case Studies - RFID for Pallet Tracking</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="case-studies">
    <div style="text-align: center">
        <h1>Case Studies</h1>
        <p>We offer our service “RFID Solution” to support your company.</p>
    </div>
    <p>
        <b>BACKGROUND</b>
        <br>
        PT XXX wants to monitor thousand of their pallet in warehouse, when it’s come last time and when it’s goes from warehouse. They rent thousands of pallets but actually didn’t know how many pcs used.
    </p>
    <p>
        <b>SOLUTIONS</b><br>
        • By Implement a RFID technology, we hope can solve their problem<br>
        • Tracked all pallet and install (RFID Reader) – for detect In Out Time<br>
        • Web Dashboard Monitoring – Where & When , Time in Out
    </p>
    <p>
        <b>Warehouse Layout</b>
        <img src="/src/img/case-studies/cs4.png" alt="Case Studies" style="width: 100%;max-width: 800px;display: block;">
    </p>
    <h3>Detail Process</h3>
    <div class="parameter">
        <table>
            <tr class="title-table">
                <td>No</td>
                <td>Task</td>
                <td>Description</td>
                <td>Process</td>
            </tr>
            <tr>
                <td>1</td>
                <td>Gate In / Read Tag</td>
                <td>Read the Tag when come to room and continues update the time when inside</td>
                <td>Record time</td>
            </tr>
        </table>
    </div>
</div>

<style>
    .jumbo{
        position: relative;
        margin: 0;
        background: #0065a8 url('/src/img/jumbo/case-studies.jpg') bottom no-repeat;
        background-size: cover;
        filter: brightness(.9) contrast(.9);
        height: 50vh;
    }
    .case-studies{
        width: calc(100% - 32px);
        max-width: 800px;
        margin: 0 auto;
        padding: 24px 16px;
    }
    .case-studies h1{
        margin: 0 0 16px 0;
    }
    .case-studies img{
        width: auto;
    }
    h3{
        margin: 32px 0 8px 0;
        letter-spacing: 0;
    }
    @media(max-width: 600px){
        .case-studies h1{
            font-size: 28px;
        }
        .jumbo{
            height: 256px;
        }
    }
    td:first-child{
        width: auto;
        text-align: center;
    }
    td:nth-child(2){
        width: 25%;
    }
    td:last-child{
        width: 25%;
    }
</style>