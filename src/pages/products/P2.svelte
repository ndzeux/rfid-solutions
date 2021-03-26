<script>
    // import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Products - UHF RFID Fixed Reader</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>DETAIL PRODUCTS</h1>
    </div>
    <div class="name row between-xs middle-xs">
        <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12">
            <h2>UHF RFID Fixed Reader</h2>
            <br>
            <span>* Reading distance depond on Antenna gain (dBi) from 3 up to 20 meters</span>
        </div>
        <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12 row middle-xs center-xs">
            <img src="/src/img/products/p2-1.png" alt="Fixed Reader">
        </div>
    </div>
    <div class="feature">
        <h3>Product features:</h3>
        <ul style="margin: 0 0 0 16px;padding: 0;">
            <li>The shell is made of high strength pressure casting aluminum material, patent appearance design,strong and durable to meet the requirements of harsh working environment;</li>
            <li>Use Impinj Indy R2000 UHF RFID chip to achieve excellent stability and strong muti-tag long-distance recognition performance, TI ARM embedded processing chip realizes high-speed reading and fast data calculation;</li>
            <li>Comply with EPC global UHF Class 1 Gen 2 / ISO 18000-6C/ ISO18000-6B protocol tags;</li>
            <li>Work frequency in 865-868MHZ，902-928MHZ( customized optional);</li>
            <li>Certified by FCC, CE and applicated in warehouse logistic supply chain, asset tracking, transportation, manufacture etc.;</li>
            <li>Support Wiegand, RS232, RS485, TCP/IP and wireless communication;</li>
            <li>RF output 33dbm adjustable, build with auto mode, command mode, Trigger mode etc.;</li>
            <li>Read buzzer and LED indicator, support firmware upgrade online;</li>
            <li>Provide many I/O input and output port to do easily application integrated.</li>
        </ul>
    </div>
    <br>
    <div class="parameter">
        <table>
            <tr class="title-table">
                <td>Performance Index
                <td></td>
            </tr>
            <tr>
                <td>RF core chip</td>
                <td>Indy R2000</td>
            </tr>
            <tr>
                <td>Protocol</td>
                <td>EPC Global UHF class1 Gen2/ISO 18000-6C/ISO 18000-6B</td>
            </tr>
            <tr>
                <td>Work frequency</td>
                <td>902-928MHz or 865-868MHz</td>
            </tr>
            <tr>
                <td>RF output</td>
                <td>33dBm±1dBm</td>
            </tr>
            <tr>
                <td>Receive sensitivity</td>
                <td>＜﹣85dBm</td>
            </tr>
            <tr>
                <td>Tag reading speed</td>
                <td>＞800 times/second</td>
            </tr>
            <tr>
                <td>Tag reading distance</td>
                <td>0-25m ( depend on reader parameter set, antenna gain, tag type etc.)</td>
            </tr>
            <tr>
                <td>Tag writing distance</td>
                <td>Tag writing distance	0-10m ( depend on reader parameter set, antenna gain, tag type etc.)</td>
            </tr>
            <tr>
                <td>Tag RSSI</td>
                <td>Support</td>
            </tr>
            <tr>
                <td>Antenna connect protection	Support</td>
                <td>Support</td>
            </tr>
            <tr>
                <td>Support area</td>
                <td>USA and Canada and other comply with FCC Part 15 area
                    Europe and other comply with ETSI EN 302 308 area
                    China, India, Japan, Korea, Malaysia etc.
                    </td>
            </tr>
            <tr>
                <td>Antenna ports</td>
                <td>4 TNC antenna ports</td>
            </tr>
            <tr>
                <td>Communication port</td>
                <td>10M/100M tcp/ip internet, RS232,RS485,Wiegand26/34</td>
            </tr>
            <tr>
                <td>WiFi (option)</td>
                <td>Support EEE 802.11 n/b/g</td>
            </tr>
            <tr>
                <td>Bluetooth (option)</td>
                <td>Support Bluetooth 4.0</td>
            </tr>
            <tr>
                <td>Communication rate</td>
                <td>RS232 with 9600～115200bps，RJ45 with 10Mbps</td>
            </tr>
            <tr>
                <td>Reliable upgrade</td>
                <td>Reliable upgrade	upgrade mechanism can be extended</td>
            </tr>
            <tr>
                <td>Input/output</td>
                <td>2 input, 1 output</td>
            </tr>
            <tr>
                <td>SDK language</td>
                <td>VC, VB, JAVA, C#, C++ etc.</td>
            </tr>
            <tr class="title-table">
                <td>Mechanical and Electrical Performance</td>
                <td></td>
            </tr>
            <tr>
                <td>Unit dimension</td>
                <td>200(length)*200 (width)*35(height)mm</td>
            </tr>
            <tr>
                <td>Power supply</td>
                <td>With 220V AC input, the output of +12 V/3A DC power converter</td>
            </tr>
            <tr>	
                <td>Reader antenna port type</td>
                <td>TNC Female connector</td>
            </tr>
            <tr>
                <td>Weight</td>
                <td>Reader antenna port type</td>
            </tr>
            <tr>
                <td>Humidity</td>
                <td>5% to 95%,  Non-condensing</td>
            </tr>
            <tr>
                <td>IP protection</td>
                <td>IEC IP51</td>
            </tr>
            <tr>
                <td>Work temperature</td>
                <td>-20 ºC to +60 ºC</td>
            </tr>
            <tr>
                <td>Storage temperature</td>
                <td>-40°C to 80°C</td>
            </tr>
            <tr>
                <td>Certificate</td>
                <td>FCC, CE</td>
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