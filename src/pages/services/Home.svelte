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
    <div class="row center-xs">
        <a class="box col-lg-4 col-md-4 col-sm-6 col-xs-12" href="/services/manage-services">
            <h3 class="row middle-xs center-xs">Managed Services</h3>
            Let’s we care your whole RFID Solution system and Daily Operation in one solution. We prevent your problem before they arise and you can focus on your Strategic Business.
        </a>
        <a class="box col-lg-4 col-md-4 col-sm-6 col-xs-12" href="/services/professional-services">
            <h3 class="row middle-xs center-xs">Professional Services</h3>
            We provide a new RFID software development for specific challenges through a dedicated project. We offer professional services for business that need immediate help for a specific pain point or problem, including planning strategically for your future growth
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
        margin: 0;
    }
    .products > .row a{
        color: inherit;
    }
    .products h3{
        margin: 12px 0 4px 0;
    }
    .products > .row{
        margin: 0;
    }
    @media(max-width: 600px){
        .jumbo{
            height: 256px;
        }
    }
</style>