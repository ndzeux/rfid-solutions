<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Case Studies - RFID for Faster Inbound, Outbound, Cashier Process</title>
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
        PT XYZ wants to improve Inbound – outbound process in their warehouse. The existing process in their warehouse describe below: 
        <br>
        • The current problem is WHS Staff must scan one-by-one item in warehouse gate-in. They have 10.000-20.000 SKU’s received per day; it does will take a time and more resources. 
        <br>
        • Agility have 4- 6 staff for Sales Order process in Warehouse, When WHS Staff want to pick up the order, the order should be check by cashier in which per 1 box consist of 10 Pcs, She/he will open the box and check one-by-one.
        <br>
        • Concern to effective and efficient time with IoT they hope will help their business         
    </p>
    <p>
        <b>SOLUTIONS</b><br>
        • By Implement a RFID technology, we hope can solve their problem<br>
        • Counting Inventory Faster, Cashier Process Easier, Effective and Reduce Time & Cost
    </p>
    <p>
        <b>Warehouse Layout</b>
        <img src="/src/img/case-studies/cs2.png" alt="Case Studies" style="width: 100%;max-width: 800px;display: block;">
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
                <td>Inbound Process Goods with RFID Attached bring to WHS (Gate in)</td>
                <td>
                    Goods come to warehouse (Installed RFID Reader in Gate In)<br>
                    *Collective scan should in same SKU (Per Pallet or Box)</td>
                <td>All RFID Tag will be read</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Register Item</td>
                <td>Register Item – Using Batch Process or One – by – One</td>
                <td></td>
            </tr>
            <tr>
                <td>3</td>
                <td>Staff Check Receiving Goods & Put Way</td>
                <td>Staff will see is there some goods come to Warehouse. Then, using Web Desktop / Android App for putting away , update the Location, Rack & BIN information</td>
                <td>Put way Activity</td>
            </tr>                
            <tr>
                <td>4</td>
                <td>Process SO / Cashier</td>
                <td>Cahier will scan goods per Box, and Confirm the item is match with Order No.</td>
                <td>Cashier should check Order Detail</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Outbound Process</td>
                <td>Goods scanned by RFID Reader in Gate Out<br>
                    *Check if the Goods, it’s not process by cashier then will rise alarm / Notify to Warehouse manager via Telegram    
                </td>
                <td>Alert System , When Goods out but did not process in Cashier</td>
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