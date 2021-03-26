<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Case Studies - RFID for Stock Monitoring</title>
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
        PT XYZ will implement a RFID solution for Inventory monitoring system in warehouse to improve process more effective and efficient, easy & faster stock checking. Using the RFID with low cost alternative technology we can offer the solution below.
    </p>
    <p>
        <b>Warehouse Layout</b>
        <img src="/src/img/case-studies/cs1.png" alt="Case Studies" style="width: 100%;max-width: 800px;display: block;">
    </p>
    <h3>Detail Process</h3>
    <div class="parameter">
        <table>
            <tr class="title-table">
                <td>No</td>
                <td>Task</td>
                <td>Description</td>
                <td>Remark</td>
            </tr>
            <tr>
                <td>1</td>
                <td>Process GR</td>
                <td>Staff Doing GR Process in SAP System</td>
                <td></td>
            </tr>
            <tr>
                <td>2</td>
                <td>Get RFID  & Register Items</td>
                <td>Staff request RFID from RFID Keeper<br>
                    Register Item to System (using Web / Handheld)</td>
                <td><b>Optional:</b><br>
                    Printing RFID Tag</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Goods with RFID Attached bring to WHS (Gate in)</td>
                <td>In front of door we install a RFID Reader to read the goods.</td>
                <td>Data Automatic Send to Cloud Server</td>
            </tr>                
            <tr>
                <td>4</td>
                <td>Staff Check Receiving Goods & Put Way</td>
                <td>Staff will see is there some goods come to Warehouse. Then, using Web Desktop / Android App, He checking RFID read by Gate and Pair with Goods Information (Item Name and Location Rack & BIN)</td>
                <td>Put way Activity</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Scanning Routine</td>
                <td>Staff will do daily scanning RFID to make sure that the goods still inside warehouse by using Handheld</td>
                <td>Daily Scanning</td>
            </tr>
            <tr>
                <td>6</td>
                <td>Scanning for Pickup</td>
                <td>Staff will scan the RFID before Pickup to make sure that goods is match</td>
                <td>Scanning Detail Information before Pickup</td>
            </tr>
            <tr>
                <td>7</td>
                <td>Goods bring out from WHS (Gate in)</td>
                <td>In front of door we install a RFID Reader to read the goods.</td>
                <td>Data Automatic Send to Cloud Server</td>
            </tr>
            <tr>
                <td>8</td>
                <td>Staff Check Out Goods & Confirmation</td>
                <td>Staff will final check to make sure the goods it’s not wrong and do confirmation</td>
                <td>Goods will be delete from monitoring table</td>
            </tr>
        </table>
    </div>
    <h3>Solution Cloud, Web Monitoring & Android Apps</h3>
    <div class="parameter">
        <table>
            <tr class="title-table">
                <td>No</td>
                <td>Solution</td>
                <td>Description</td>
                <td>Remark</td>
            </tr>
            <tr>
                <td>1</td>
                <td>RFID Cloud Server</td>
                <td>Cloud Server to save all RFID Tag read by Reader</td>
                <td></td>
            </tr>
            <tr>
                <td>2</td>
                <td>Web Monitoring</td>
                <td>Web monitoring:  Goods Received, Goods Daily Monitoring, Goods Pickup</td>
                <td></td>
            </tr>
            <tr>
                <td>3</td>
                <td>Android Apps</td>
                <td>Android app for checking daily scan & Goods detail information when goods will be picked up</td>
                <td>• Register Item with Read Tag<br>
                    • Scan Inventory for Monitoring<br>
                    • Scan Inventory for Pickup</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Android Apps</td>
                <td>Android apps for searching inventory, receive confirmation / put way  and picked up confirmation</td>
                <td>• Searching Item<br>
                    • Inventory Put way<br>
                    • Picking Confirmation</td>
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