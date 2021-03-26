<script>
    import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>PRODUCTS</h1>
        <span style="color: #777">RFID products: RFID readers, RFID tags, RFID antennas, RFID printers, RFID Handheld, Active RFID</span>
        <p>
            Printers, Encoders, Readers, and accessories to go with your current or future RFID system. RFIDsolutions require many pieces working together and RFIDSolutions.id has the knowledgeable professionals with the experience your business is looking for. Below we have provided a few of our top RFID products.
        </p>
        <span style="color:#0065a8">
            READY TO PURCHASE RFID PRODUCTS?<br>
            CALL US AT 021-80879546
        </span>
    </div>
    <div class="row center-xs">
        <a use:link href="/products/uhf-rfid-integrated-reader" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p1.png" alt="Products">
            </div>
            <h3>UHF RFID Integrated Reader</h3>
            <span>【7dBi/9dBi/12dBi】</span>
        </a>
        <a use:link href="/products/uhf-rfid-fixed-reader" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p2.png" alt="Products">
            </div>
            <h3>UHF RFID Fixed Reader</h3>
            <span>【7dBi/9dBi/12dBi】</span>
        </a>
        <a use:link href="/products/uhf-rfid-antenna" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p3.png" alt="Products">
            </div>
            <h3>UHF RFID Antenna</h3>
            <span>【7dBi/9dBi/12dBi】</span>
        </a>
        <a use:link href="/products/uhf-rfid-tag" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p4.jpg" alt="Products">
            </div>
            <h3>UHF RFID Tag</h3>
            <span>【Tags】</span>
        </a>
        <a use:link href="/products/uhf-rfid-handheld-reader" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p5.png" alt="Products">
            </div>
            <h3>UHF RFID Handheld Reader</h3>
            <span>【Mobile】</span>
        </a>
        <a use:link href="/products/uhf-rfid-desktop-reader" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p6.png" alt="Products">
            </div>
            <h3>UHF RFID Desktop Reader</h3>
            <span>【Desktop】</span>
        </a>
        <a use:link href="/products/uhf-rfid-printer" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p7.jpg" alt="Products">
            </div>
            <h3>UHF RFID Printer</h3>
            <span>【Printer】</span>
        </a>
        <a use:link href="/products/2-45g-active-rfid" class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <div class="img row middle-xs center-xs">
                <img src="/src/img/products/p8.jpg" alt="Products">
            </div>
            <h3>2.45G Active RFID</h3>
            <span>【Active RFID】</span>
        </a>
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
    .products .row > a{
        text-align: center;
        color: inherit;
        padding: 12px 8px;
    }
    .products .img{
        padding: 6px;
        margin: 0;
        height: 200px;
        border: 1px solid #ddd;
        transform: scale(.8);
        transition: transform .3s;
    }
    .products .img:hover{
        transform: scale(1);
    }
    .products img{
        max-width: 150px;
        width: auto;
    }
    @media(max-width: 600px){
        .jumbo{
            height: 256px;
        }
    }
</style>