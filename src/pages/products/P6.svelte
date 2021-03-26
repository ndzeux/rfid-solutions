<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products - UHF RFID Dekstop Reader</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>DETAIL PRODUCTS</h1>
    </div>
    <div class="name row between-xs middle-xs">
        <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <h2>UHF RFID Dekstop Reader</h2>
        </div>
        <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12 row middle-xs center-xs">
            <img src="/src/img/products/p6-1.png" alt="Dekstop Reader">
        </div>
    </div>
    <div class="intro">
        <h3>Product feature:</h3>
        (1) Full support for compliance with ISO-18000-6B, ISO-18000-6C (EPC G2) standards;
        <br>
        (2) Working frequency 902-928Mhz or 865-868Mhz (can be adjusted according to different country or region requirements);
        <br>
        (3) With emulation keyboard function, computer USB interface for power supply, blue radio frequency indicator light and buzzer operation;
        <br>
        (4) It has advantages of small size and fast reading rate. It can perform operations such as authorization, report loss, and programming on tags, and can be widely used in various RFID systems;
        <br>
        (5) Application areas: The system has been widely used in clubs, libraries, student status, consumption management, attendance management, dining management, swimming pool management and other systems.    
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
                <td>Working frequency 902-928MHZ or 865-868MHZ (can be adjusted according to different countries or regions)</td>
            </tr>
            <tr>
                <td>Frequency modulation method</td>
                <td>Broad spectrum frequency modulation (FHSS) or fixed frequency, which can be set by software</td>
            </tr>
            <tr>
                <td>Number of antennas</td>
                <td>Built-in double-feed point ceramic antenna</td>
            </tr>
            <tr>
                <td>Communication</td>
                <td>Interface	USB</td>
            </tr>
            <tr>
                <td>Application software interface</td>
                <td>Provide dynamic link library (DLL) to support secondary development</td>
            </tr>
            <tr class="title-table">
                <td>Label operation performance</td>
                <td></td>
            </tr>
            <tr>
                <td>Reading distance</td>
                <td>Built-in transceiver antenna, reading distance >30cm, writing distance >10cm</td>
            </tr>
            <tr>
                <td>Air interface protocol</td>
                <td>Support compliance with ISO-18000-6B, ISO-18000-6C (EPC G2)</td>
            </tr>
            <tr class="title-table">
                <td>Mechanical electrical performance</td>
                <td></td>
            </tr>
            <tr>
                <td>size</td>
                <td>139(L)*86(W)*22(H)mm</td>
            </tr>
            <tr>
                <td>power supply</td>
                <td>Computer USB interface for power</td>
            </tr>
            <tr>
                <td>weight</td>
                <td>120g</td>
            </tr>
            <tr>
                <td>humidity</td>
                <td>5% to 95%, non-condensing</td>
            </tr>
            <tr>
                <td>Protection class</td>
                <td>IEC IP52</td>
            </tr>
            <tr>
                <td>Operating temperature</td>
                <td>-20 ºC to 60  ºC</td>
            </tr>
            <tr>
                <td>storage temperature</td>
                <td>-40°C to 80°C</td>
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