<script>
    import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Solutions</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>SOLUTIONS</h1>
        <p style="font-weight:bold;font-size:18px">
            RFID solutions that let you track, control and manage all critical resources
        </p>
    </div>
    <div class="image">
        <img src="/src/img/solutions/desktop.jpg" alt="RFID Desktop">
    </div>
    <div class="row center-xs">
        <div class="box col-lg-4 col-md-4 col-sm-6 col-xs-12">
            <h3 class="row middle-xs center-xs">Warehouse Inventory Management</h3>
            RFID Inventory Management system with RFIDSolutions.id software, Improve visibility and reliability in your supply chain and logistics. Reduce warehouse handling time & costs: when receiving, put way, searching, picking, cashier operations, stock opname counting.
        </div>
        <div class="box col-lg-4 col-md-4 col-sm-6 col-xs-12">
            <h3 class="row middle-xs center-xs">Attendance Tracking</h3>
            RFID attendance tracking system with RFIDSolutions.id software, offers increased visibility in real time, record time attendance of employee, student, or labor with detecting when they come or out from office / school / project site.
        </div>
        <div class="box col-lg-4 col-md-4 col-sm-6 col-xs-12">
            <h3 class="row middle-xs center-xs">Asset Tracking</h3>
            RFID asset tracking system with RFIDSolutions.id software, offers increased visibility in real time, with detecting the Tags in location that UHF RFID reader installed.
        </div>
    </div>
</div>

<style>
    .jumbo{
        position: relative;
        margin: 0;
        background: #0065a8 url('/src/img/jumbo/products.jpg') center no-repeat;
        background-size: cover;
        filter: brightness(.8) contrast(.8);
        height: 50vh;
    }
    .products{
        width: calc(100% - 32px);
        max-width: 1328px;
        margin: 0 auto;
        padding: 24px 16px;
    }
    .products h1{
        margin: 0 0 16px 0;
    }
    .products h3{
        margin: 12px 0 4px 0;
    }
    .products > .row{
        margin: 24px 0 0 0;
    }
    .products .image{
        margin-top: 16px;
        text-align: center;
    }
    .image img{
        width: 30vw;
        min-width: 360px;
        height: auto;
        border-radius: 16px;
        box-shadow: 0 2px 4px rgba(0,0,0,.12);
    }
    @media(max-width: 600px){
        .jumbo{
            height: 256px;
        }
        .image img{
            width: calc(100% - 16px);
            min-width: auto;
        }
    }
</style>