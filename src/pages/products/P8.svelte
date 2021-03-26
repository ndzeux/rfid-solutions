<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products - 2.45 Active RFID</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>DETAIL PRODUCTS</h1>
    </div>
    <div class="name row between-xs middle-xs">
        <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <h2>2.45 Active RFID</h2>
        </div>
        <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12 row middle-xs center-xs">
            <img src="/src/img/products/p8.jpg" alt="2.45G Active RFID">
        </div>
    </div>
    <div class="intro">
        <h3>Profile:</h3>
        <ul style="padding: 0;margin: 0 0 0 16px;">
            <li>The shell is made of high strength die-cast aluminum, rugged, can work long-term in harsh environment.</li>
            <li>Idea of low-power, low-voltage design  ensure the product safe and stable operation long term without failure;</li>
            <li>monitoring software for running status, 24 hours running X365 without crash</li>
            <li>VF-721 2.4GHz active RFID reader is a high performance RFID reader, with long distance reading , high recognition accuracy and strong anti-collision.</li>
            <li>The active RFID reader is mainly used in vehicle management, intelligent transportation, electric vehicle anti-theft system, safe campus, safe home and school, asset management, warehousing and logistics management.</li>
        </ul>    
    </div>
    <div class="feature">
        <h3>Product features</h3>
        1. Reading distance up to 100 meters
        <br>
        2. Recognition accuracy rate: 99.9%;
        <br>
        3. Anti-collision ability: read the card more than 200 in 3 seconds
        <br>
        4. Read labels saved to the buffer;
        <br>
        5. Reading distance up to 100 meters, the special tag up kilometers;
        <br>
        6. Recognition accuracy rate: 99.9%;
        <br>
        7. Anti-collision ability: read tag more than 200 in 3 second
        <br>
        8. Read tag ID can be saved to the buffer;
        <br>
        9. After reading tag, able to notify the user via LED, buzzer, status signal relay outputs
        <br>
        10. After reading tag, can be transferred to the host computer via RS232 and LAN port;
        <br>
        11. Communication mode has active and passive transfer transmission;
        <br>
        12. RS232, RS485 communication rate can be set;
        <br>
        13. Set the output gain of the reader through software to adjust reading distance;
        <br>
        14. With same tag, reading interval can be set;
        <br>
        15. Tag initiative upload speed can be set;
        <br>
        16. External trigger to read the tag information;
    </div>
    <br>
    <div class="parameter">
        <h3>Specification</h3>
        <table>
            <tr class="title-table">
                <td>Mechanical Performance Indicators</td>
                <td></td>
            </tr>
            <tr>
                <td>working frequency</td>
                <td>2.4GHz-2.5GHz</td>
            </tr>
            <tr>
                <td>working mode</td>
                <td>Active and passive binding</td>
            </tr>
            <tr>
                <td>structure</td>
                <td>The shell is made of high strength die-cast aluminum, rugged, good to work long term and radiating</td>
            </tr>
            <tr>
                <td>communication</td>
                <td>Interface RS232, LAN port</td>
            </tr>
            <tr>
                <td>communication method</td>
                <td>Active mode (after reading tag, automatically send data to host)</td>
            </tr>
            <tr>
                <td>identification distance</td>
                <td>100 meters</td>
            </tr>
            <tr>
                <td>recognition accuracy</td>
                <td>99.9%</td>
            </tr>
            <tr>
                <td>Software Interface</td>
                <td>Provide demonstration software, API functions, etc.</td>
            </tr>
            <tr>
                <td>Output format</td>
                <td>can customize a variety of data output format according to user requirements</td>
            </tr>
            <tr>
                <td>Diverse read ways</td>
                <td>Readable and writable, read directly and controlled reading</td>
            </tr>
            <tr>
                <td>RF output interface</td>
                <td>1 SMA female  antenna interfaces; 2 SMA female antenna interface; 4 SMA female antenna interface</td>
            </tr>
            <tr>
                <td>Working Voltage</td>
                <td>DC9-12V</td>
            </tr>
            <tr>
                <td>Working current</td>
                <td>Less 200mA</td>
            </tr>
            <tr>
                <td>Operating temperature</td>
                <td>-25℃ ～ +75℃</td>
            </tr>
            <tr>
                <td>Storage Temperature (℃)</td>
                <td>-40℃ ～ +85℃</td>
            </tr>
            <tr>
                <td>Working humidity</td>
                <td>Less 95％</td>
            </tr>
            <tr>
                <td>Packaged Size</td>
                <td>235(length)*211 (width)*40(height)mm</td>
            </tr>
            <tr>
                <td>Weight</td>
                <td>2.5kg;</td>
            </tr>
            <tr>
                <td>Certificate</td>
                <td>FCC,CE</td>
            </tr>
            <tr class="title-table">
                <td>Antenna Performance Indicators</td>
                <td></td>
            </tr>
            <tr>
                <td>Gain</td>
                <td>10dBi</td>
            </tr>
            <tr>
                <td>Antenna type</td>
                <td>Rod or plate type</td>
            </tr>
            <tr>
                <td>Horizontal beam width</td>
                <td>30°</td>
            </tr>
            <tr>
                <td>Vertical Beam width</td>
                <td>25°</td>
            </tr>
            <tr>
                <td>Front to back ratio</td>
                <td>>25dB</td>
            </tr>
            <tr>
                <td>VSWR</td>
                <td>&lt;1.5</td>
            </tr>
            <tr>
                <td>Polarization direction</td>
                <td>Circular polarization></td>
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
        max-height: 256px;
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