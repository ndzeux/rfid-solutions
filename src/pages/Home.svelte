<script>
    import { link } from 'svelte-routing'
    let t
    let b
    function slideClients(e, z){
        t = e.target
        b = [t.parentNode.parentNode.querySelector(".b1"), t.parentNode.parentNode.querySelector(".b2"), t.parentNode.parentNode.querySelector(".b3")]
        t.parentNode.querySelectorAll("span").forEach(s => s.style.cssText = "")
        b.forEach(bb => bb.style.display = "none")
        t.style.cssText = "background:#006588;border:1px solid #006588"
        if(z == 1){
            b[0].style.display = ""
        } else if(z == 2){
            b[1].style.display = ""
        } else if(z == 3){
            b[2].style.display = ""
        }
    }
</script>

<svelte:head>
    <title>RFID Solutions</title>
</svelte:head>

<div class="jumbo">
    <h1 class="row middle-xs center-xs">Use RFID Technology to help your business<br>
        Make it easier, faster and reduce cost</h1>
</div>
<div class="solutions">
    <h2>RFID Solutions</h2>
    RFID solutions that let you track, control and manage all critical resources
    <div style="text-align:center">
        <img src="/src/img/home/1.png" alt="RFID Solutions">
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
<div class="products">
    <h2>RFID Products</h2>
    <div class="row between-xs">
        <div class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <img src="/src/img/home/p1.png" alt="RFID Products">
            <h3>UFH RFID Reader</h3>
            UHF RFID integrated reader, fixed reader with variant antenna gain 7dBi/9dBi/12dBi, Excellent UHF reading and writing performance, Adopt ISO-18000-6B, ISO-18000-6C (EPC G2), Perfect integration of antenna and RF reader
        </div>
        <div class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <img src="/src/img/home/p2.png" alt="RFID Products">
            <h3>UHF RFID Antenna</h3>
            Antenna gain 7dBi/9dBi/12dBi , Working frequency 902-928MHZ(can be adjusted according to different countries or regions).
        </div>
        <div class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <img src="/src/img/home/p3.png" alt="RFID Products">
            <h3>UHF RFID Tags</h3>
            Hundred of kind tags, depand on project need, asset tracking, attendance tracking, inventory tracking
        </div>
        <div class="box col-lg-3 col-md-3 col-sm-6 col-xs-12">
            <img src="/src/img/home/p4.png" alt="RFID Products">
            <h3>Mobile RFID Reader</h3>
            Mobile UHF RFID reader for mobile android application.
        </div>
    </div>
    <a href="/products" use:link>View All Products</a>
</div>
<div class="onw row between-xs">
    <div class="left col-lg-6 col-md-6 col-sm-6 col-xs-12 first-sm last-xs">
        <h2>Our Clients</h2>
        Trusted by largest companies and government organizations
        <div class="b1 row between-xs">
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/unilever.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/ae.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/detpak.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/schenker.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/gmf.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/sumber-prima.png" alt="Clients">
            </div>
        </div>
        <div class="b2 row between-xs" style="display: none">
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/hankyu.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/hm-sampoerna.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/kbn.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/lautan-luas.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/manuppak.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/nippon.png" alt="Clients">
            </div>
        </div>
        <div class="b3 row between-xs" style="display:none">
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/gudang-garam.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/erafista.png" alt="Clients">
            </div>
            <div class="box col-xs-4 row middle-xs center-xs">
                <img src="/src/img/clients/sgl.png" alt="Clients">
            </div>
            <div class="box col-xs-6 row middle-xs center-xs" style="max-width: calc(50% - 16px);">
                <img src="/src/img/clients/pindad.png" alt="Clients">
            </div>
            <div class="box col-xs-6 row middle-xs center-xs" style="max-width: calc(50% - 16px);">
                <img src="/src/img/clients/tenaris.png" alt="Clients">
            </div>
        </div>
        <div class="bullets">
            <span style="background:#006588;border:1px solid #006588" on:click={e => slideClients(e, 1)}></span><span on:click={e => slideClients(e, 2)}></span><span on:click={e => slideClients(e, 3)}></span>
        </div>
    </div>
    <div class="right col-lg-6 col-md-6 col-sm-6 col-xs-12">
        <h2>Who we are ?</h2>
        <p>RFIDSolutions.id is a RFID product and solution of PT Logika Pratama, delivers cloud RFID solutions and RFID hardware. Our identification & tracking solutions ensure operational efficiency and improve control over your assets.</p>
        <p>We are energic and young team with enthusiast of technology IoT. We can deliver the solution to the customers both for device and platform with wide of range experience in device protocol programming and software design.</p>
        <p>Your business system may require a stand-alone or integrated software solution and we have the experienced RFID architects and technical engineers to implement and support your RFID solutions</p>
        <a href="/solutions" use:link>Learn More</a>
        <br><br>
    </div>
</div>

<style>
    .jumbo{
        position: relative;
        margin: -72px 0 0 0;
        background: #0065a8 url('/src/img/jumbo/home.jpg') center no-repeat;
        background-size: cover;
        height: 80vh;
    }
    .jumbo h1{
        margin: 0;
        padding: 0 32px;
        position: absolute;z-index: 2;
        top: 0;right: 0;bottom: 0;left: 0;
        background: rgba(0, 72, 121, 0.2);
        color: #fff;
    }
    @media(max-width: 500px){
        .jumbo{
            height: 50vh;
        }
        .jumbo h1{
            padding-top: 32px;
            font-size: 25px;
        }
    }

    .solutions{
        width: calc(100% - 32px);
        max-width: 1328px;
        margin: 0 auto;
        padding: 24px 16px;
        text-align: center;
        color: #777;
    }
    .solutions > div{
        margin: 0 -12px;
    }
    .solutions > div h3{
        color: #333;
        font-size: 24px;
        margin: 0 0 8px 0;
        height: 74px;
    }
    @media(max-width:1280px){
        .solutions > div h3{
            height: auto;
        }
    }
    @media(max-width:978px){
        .solutions > div h3{
            height: 74px;
        }
        .solutions > div > div+div+div h3{
            height: auto;
        }
    }
    @media(max-width:720px){
        .solutions > div h3{
            height: auto;
        }
    }
    .solutions > div .box{
        color: #444;
        text-align: justify;
        padding: 16px;
    }
    .solutions h2{
        font-size: 44px;
        color: #0065a8;
        margin: 0 0 8px 0;
    }
    .solutions img{
        width: 100%;
        max-width: 1000px;
    }
    .products{
        padding: 32px calc((100vw - 1360px) / 2 + 8px);
        background: #0065a8;
        text-align: center;
        color: #fff;
        margin: 0
    }
    .products h2{
        font-size: 44px;
        margin: 0 0 32px 0;
    }
    .products img{
        height: 128px;
        width: auto;
    }
    .products > div{
        margin: 0
    }
    .products > div > .box{
        padding: 16px;
    }
    .products > a{
        display: inline-block;
        margin: 16px 0 8px 0;
        padding: 12px 16px;
        border-radius: 8px;
        background: #fff;
        color: #0065a8;
        border: 1px solid #fff;
        transition: color .3s, background .3s;
    }
    .products > a:hover{
        color: #fff;
        background: #0065a8;
    }
    .onw{
        background: #fafafa;
        margin: 0;
        padding: 32px calc((100vw - 1360px) / 2 - 16px);
    }
    .onw h2{
        font-size: 40px;
        color: #0065a8;
        margin: 0;
    }
    .onw > div{
        padding: 0 16px
    }
    .onw .left{
        text-align: center;
    }
    .onw .left > div{
        margin: 16px 0 0 0
    }
    .onw .left > div > div{
        padding: 12px;
        margin: 8px;
        height: 120px;
        background: #fff;
        border: 1px solid #eee;
        max-width: calc(33.333% - 16px);
    }
    @media(max-width: 440px){
        .onw .left > div > div{
            height: 80px;       
        }
    }
    .onw .left img{
        max-width: 100%;
        width: auto;
        max-height: 100%;
        height: auto;
    }
    .onw .left .bullets{
        display: block;
        text-align: center;
    }
    .onw .left .bullets span{
        display: inline-block;
        width: 20px;height: 20px;
        background: #fff;
        margin: 0 8px;
        border: 1px solid #ddd;
        border-radius: 100%;
        cursor: pointer;
    }
    .onw .right > a{
        display: inline-block;
        margin: 16px 0 8px 0;
        padding: 12px 16px;
        border-radius: 8px;
        background: #0065a8;
        color: #fff;
        border: 1px solid #0065a8;
        transition: color .3s, background .3s;
    }
    .onw .right > a:hover{
        color: #0065a8;
        background: #fff;
    }
</style>