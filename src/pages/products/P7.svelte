<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products - UHF RFID Printer</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>DETAIL PRODUCTS</h1>
    </div>
    <div class="name row between-xs middle-xs">
        <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <h2>UHF RFID Printer</h2>
        </div>
        <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12 row middle-xs center-xs">
            <img src="/src/img/products/p7.jpg" alt="Dekstop Reader">
        </div>
    </div>
    <div class="intro">
        <h3>Profile:</h3>
        <ul style="padding: 0;margin: 0 0 0 16px;">
            <li>Ultra-small tag reader: supports a minimum height of 12 mm print RFID tag reader;</li>
            <li>100% pass rate Tags: read-write check after the original first printing technology, complete the testing process all bad label;</li>
            <li>One key location: one key to locate the position of the tag antenna, automatic detection of the best area to read and write;</li>
            <li>First print: Supports a variety of RFID tags first print size, label zero waste.</li>
        </ul>    
    </div>
    <br>
    <div class="parameter">
        <h3>Specification</h3>
        <table>
            <tr class="title-table">
                <td>Item numer</td>
                <td>VPR-0407 UHF RFID PRINTER</td>
            </tr><tr>
                <td>Printing </td>
                <td>Thermal transfer</td>
            </tr>
            <tr>
                <td>Resolution</td>
                <td>300 dpi</td>
            </tr>
            <tr>
                <td>Max printing speed</td>
                <td>8 ips (203.2 mm/s)</td>
            </tr>
            <tr>
                <td>Max printing width</td>
                <td>4.17″ (106 mm)</td>
            </tr>
            <tr>
                <td>Max printing Length</td>
                <td>79″ (2000 mm)</td>
            </tr>
            <tr>
                <td>RFID Function (For RFID models)</td>
                <td>
                    Integrated UHF reader / encoder<br>
                    ( EPC Class 1 Gen 2/ISO 18000-6C ) </td>
            </tr>
            <tr>
                <td>Storage</td>
                <td>8 MB FLASH ROM，16 MB SDRAM</td>
            </tr>
            <tr>
                <td>Label rolls</td>
                <td>Width:<br>
                    Max 4.56″ (116 mm);<br>
                    Min 0.98" (25mm)<br>
                    Outer diameter: Max 8″ (203.2 mm);<br>
                    Inner diameter: Min 3″ (76.2 mm)</td>
            </tr>
            <tr>
                <td>Label thickness</td>
                <td>0.0024″ – 0.012″ (0.06 mm – 0.305 mm), Including backing paper thickness</td>
            </tr>
            <tr>
                <td>Ribbon Roll Size</td>
                <td>
                    Outer diameter: Max: 3.3″ (84 mm);   nner diameter: Min : 1″ (25.4 mm)<br>
                    Max width: 4.65″ (118 mm);   Max length: 1968' (600 M)<br>
                    Carbon can be inside and outside
                </td>
            </tr>
            <tr>
                <td>Paper detection methods</td>
                <td>Reflective (removable) / transmissive (moveable)</td>
            </tr>
            <tr>
                <td>Built-in fonts</td>
                <td>Western dot matrix font, vector font can be downloaded, Chinese dot-matrix font options</td>
            </tr>
            <tr>
                <td>Built-in bar code printing</td>
                <td>Code 39, Code 93, Code 128/subset A, B, C, Codabar,<br>
                    Interleave 2 of 5, UPC A/E 2 and 5 add-on,<br>
                    EAN-13/8/128, UCC-128: 1D Barcode<br>
                    <br>
                    MaxiCode, PDF417, Data Matrix, QR: 2D Barcode</td>
            </tr>
            <tr>
                <td>Interface</td>
                <td>RS-232 COM Port, 10/100 M-bit Ethernet, USB DEVICE 2.0 , USB HOST, Centronics parallel port</td>
            </tr>
            <tr>
                <td>Power Rating</td>
                <td>100 – 240 V  50/60 Hz  3.5A</td>
            </tr>
            <tr>
                <td>Weight</td>
                <td>15kgs</td>
            </tr>
            <tr>
                <td>Dimensions</td>
                <td>Width 11.3″ (286 mm) * deep 17.6″ (448 mm) *hidth11.0″ (280 mm)</td>
            </tr>
            <tr>
                <td>working environment</td>
                <td>
                    Temperature: 0 °C – 40 °C (32 °F – +104 °F)
                    <br>
                    Relative humidity: 5 % – 85 % No condensation
                </td>
            </tr>
            <tr>
                <td> Storage environment</td>
                <td>Temperature: -40 °C – 60 °C (-40 °F – +140 °F)<br>
                    Relative humidity: 5 % – 85 % No condensation</td>
            </tr>
            <tr>
                <td>Optional accessories</td>
                <td>Cutter, external label rewinding device</td>
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