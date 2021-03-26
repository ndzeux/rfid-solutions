<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products - UHF RFID Antenna</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>DETAIL PRODUCTS</h1>
    </div>
    <div class="name row between-xs middle-xs">
        <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <h2>UHF RFID Antenna</h2>
            <br>
            <span>* Reading distance depond on Antenna gain (dBi) from 3 up to 20 meters</span>
        </div>
        <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12 row middle-xs center-xs">
            <img src="/src/img/products/p3.png" alt="Antenna">
        </div>
    </div>
    <div class="feature">
        <h3>Product features:</h3>
        1. Antenna gain 9dBi;
        <br>
        2. Working frequency 902-928MHZ(can be adjusted according to different countries or regions)；
        <br>
        3. Standard with N female connector or customized;
        <br>
        4. Widely applied in RFID automatic toll parking system, warehouse management entry and exit system and etc.
    </div>
    <br>
    <div class="parameter">
        <table>
            <tr class="title-table">
                <td>Performance Index
                <td></td>
            </tr>
            <tr>
                <td>Frequency Range</td>
                <td>902-928MHZ（adjustable according to different countries or regions）</td>
            </tr>
            <tr>
                <td>Input impedance</td>
                <td>50Ω load</td>
            </tr>
            <tr>
                <td>Connector</td>
                <td>N female or customized</td>
            </tr>
            <tr>
                <td>Gain</td>
                <td>9dBi</td>
            </tr>
            <tr>
                <td>VSWR</td>
                <td>≤1.3</td>
            </tr>
            <tr>
                <td>Polarization</td>
                <td>Circular</td>
            </tr>
            <tr>
                <td>Front-to-back ratio-db</td>
                <td>≥18</td>
            </tr>
            <tr>
                <td>bandwidth</td>
                <td>26MHZ</td>
            </tr>
            <tr>
                <td>E-side lobe width -°</td>
                <td>70</td>
            </tr>
            <tr>
                <td>H-side lobe width -°</td>
                <td>65</td>
            </tr>
            <tr>
                <td>Dimension</td>
                <td>260*260*45mm</td>
            </tr>
            <tr>
                <td>Weight</td>
                <td>450G</td>
            </tr>
            <tr>
                <td>Shell material</td>
                <td>Polycarbonate plastic</td>
            </tr>
        </table>
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
        max-width: 800px;
        margin: 0 auto;
        padding: 24px 16px;
    }
    .products h1{
        margin: 0 0 16px 0;
    }
    .products .name .left span{color: #888;}
    .products .name .right{margin:0!important;}
    .products h2{
        font-size: 36px;
        margin: 0 0 -10px 0;
    }
    .products img{
        max-height: 200px;
        width: auto;
    }
    h3{
        margin: 32px 0 8px 0;
    }
    @media(max-width: 600px){
        .products h1{
            font-size: 28px;
        }
        .products h2{
            font-size: 22px;
        }
        .jumbo{
            height: 256px;
        }
    }
</style>