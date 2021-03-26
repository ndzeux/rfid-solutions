<script>
    import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Services</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>SERVICES</h1>
        <!-- <p style="font-weight:bold;font-size:18px">
            RFID solutions that let you track, control and manage all critical resources
        </p> -->
    </div>
    <div class="content">
        <h3>Managed Service System</h3>
        <p>
            Let’s we care your whole RFID Solution system and Daily Operation in one solution. We prevent your problem before they arise and you can focus on your Strategic Business.
            We providing RFID Solution Service on cloud and your Premise, Our RFID Solution provide end to end solution for your operational. All the needs packed as services; deliver to our customer based on cloud and on premise.
        </p>
        <p>
            Why chose the manage service?
            <br>
            1. Affordable cost for maintenance the system, benefit for using managed services is on cost efficiency, the company could have all own IT infrastructure and professional IT Team with huge cost but for small-medium company managed service is the best choice they no need to pay hardware, software, infrastructure , and resource
            <br>
            2. Increase efficiency, the huge cost for software ownership can be used for other project strategies
            <br>
            3. Increase Data Security handled by a professional team,
            <br>
            4. The solutions always update 
            <br>
            5. Company can focus on their business
        </p>
        <h3>Professional Services</h3>
        <p>
            We provide a new RFID software development for specific challenges through a dedicated project. We offer professional services for business that need immediate help for a specific pain point or problem, including planning strategically for your future growth.
        </p>
        <p>
            <b>Our engineer will</b> help your company plan, design, implement, and manage the right technologies to improve business productivity. (From Hardware and new Technology Code), we take the complexity out of IT solution management, so you can focus more your efforts on running your business.
        </p>
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
        margin: 0;
    }
    .products h3{
        margin: 12px 0 -12px 0;
    }
    .products .content{
        max-width: 800px;
        margin: 0 auto;
    }
    @media(max-width: 600px){
        .jumbo{
            height: 256px;
        }
    }
</style>