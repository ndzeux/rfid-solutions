<script>
    import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Professional Services</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="products">
    <div style="text-align: center">
        <h1>Professional Services</h1>
        <!-- <p style="font-weight:bold;font-size:18px">
            RFID solutions that let you track, control and manage all critical resources
        </p> -->
    </div>
    <div class="content">
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