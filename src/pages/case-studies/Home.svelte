<script>
    import { link } from "svelte-routing"
</script>

<svelte:head>
    <title>Case Studies</title>
</svelte:head>

<div class="jumbo">

</div>
<div class="case-studies">
    <div style="text-align: center">
        <h1>Case Studies</h1>
        <p>
            We offer our service “RFID Solution” to support your company.
        </p>
    </div>
    <div class="row center-xs start-xs">
        <a use:link class="col-lg-4 col-md-4 col-sm-4 col-xs-12" href="/case-studies/rfid-for-stock-monitoring">
            <svg style="width:108px;height:108px" viewBox="0 0 24 24">
                <path fill="#0065a8" d="M10 16V15H3L3 19C3 20.11 3.89 21 5 21H19C20.11 21 21 20.11 21 19V15H14V16H10M20 7H16V5L14 3H10L8 5V7H4C2.9 7 2 7.9 2 9V12C2 13.11 2.89 14 4 14H10V12H14V14H20C21.1 14 22 13.1 22 12V9C22 7.9 21.1 7 20 7M14 7H10V5H14V7Z" />
            </svg>
            <div class="row middle-xs center-xs">
                Case : RFID For Stock Monitoring
            </div>
        </a>
        <a use:link class="col-lg-4 col-md-4 col-sm-4 col-xs-12" href="/case-studies/rfid-for-faster-inbound-outbound-cashier-process">
            <svg style="width:108px;height:108px" viewBox="0 0 24 24">
                <path fill="#0065a8" d="M10 16V15H3L3 19C3 20.11 3.89 21 5 21H19C20.11 21 21 20.11 21 19V15H14V16H10M20 7H16V5L14 3H10L8 5V7H4C2.9 7 2 7.9 2 9V12C2 13.11 2.89 14 4 14H10V12H14V14H20C21.1 14 22 13.1 22 12V9C22 7.9 21.1 7 20 7M14 7H10V5H14V7Z" />
            </svg>
            <div class="row middle-xs center-xs">
                Case : RFID for faster Inbound, Outbound, Cashier Process
            </div>
        </a>
        <a use:link class="col-lg-4 col-md-4 col-sm-4 col-xs-12" href="/case-studies/rfid-for-asset-tracking-employee">
            <svg style="width:108px;height:108px" viewBox="0 0 24 24">
                <path fill="#0065a8" d="M10 16V15H3L3 19C3 20.11 3.89 21 5 21H19C20.11 21 21 20.11 21 19V15H14V16H10M20 7H16V5L14 3H10L8 5V7H4C2.9 7 2 7.9 2 9V12C2 13.11 2.89 14 4 14H10V12H14V14H20C21.1 14 22 13.1 22 12V9C22 7.9 21.1 7 20 7M14 7H10V5H14V7Z" />
            </svg>
            <div class="row middle-xs center-xs">
                Case : RFID for Asset Tracking (Employee)
            </div>
        </a>
        <a use:link class="col-lg-4 col-md-4 col-sm-4 col-xs-12" href="/case-studies/rfid-for-pallet-tracking">
            <svg style="width:108px;height:108px" viewBox="0 0 24 24">
                <path fill="#0065a8" d="M10 16V15H3L3 19C3 20.11 3.89 21 5 21H19C20.11 21 21 20.11 21 19V15H14V16H10M20 7H16V5L14 3H10L8 5V7H4C2.9 7 2 7.9 2 9V12C2 13.11 2.89 14 4 14H10V12H14V14H20C21.1 14 22 13.1 22 12V9C22 7.9 21.1 7 20 7M14 7H10V5H14V7Z" />
            </svg>
            <div class="row middle-xs center-xs">
                Case : RFID for Pallet Tracking
            </div>
        </a>
        <a use:link class="col-lg-4 col-md-4 col-sm-4 col-xs-12" href="/case-studies/rfid-for-attendance-tracking-employee-student">
            <svg style="width:108px;height:108px" viewBox="0 0 24 24">
                <path fill="#0065a8" d="M10 16V15H3L3 19C3 20.11 3.89 21 5 21H19C20.11 21 21 20.11 21 19V15H14V16H10M20 7H16V5L14 3H10L8 5V7H4C2.9 7 2 7.9 2 9V12C2 13.11 2.89 14 4 14H10V12H14V14H20C21.1 14 22 13.1 22 12V9C22 7.9 21.1 7 20 7M14 7H10V5H14V7Z" />
            </svg>
            <div class="row middle-xs center-xs">
                Case : RFID for Attendance Tracking (Employee,Student)
            </div>
        </a>
    </div>
</div>

<style>
    .jumbo{
        position: relative;
        margin: 0;
        background: #0065a8 url('/src/img/jumbo/case-studies.jpg') bottom no-repeat;
        background-size: cover;
        filter: brightness(.9) contrast(.9);
        height: 50vh;
    }
    .case-studies{
        width: calc(100% - 32px);
        max-width: 1328px;
        margin: 0 auto;
        padding: 24px 16px;
    }
    .case-studies h1{
        margin: 0 0 16px 0;
    }
    .case-studies > .row{
        margin: 24px 0 0 0;
    }
    .case-studies .row > a{
        position: relative;
        text-align: center;
        color: inherit;
        padding: 12px 8px;
        min-height: 100%;
        transition: color .3s;
    }
    .case-studies .row > a:hover{
        color: #0065a8;
    }
    .case-studies .row > a > div{
        margin: 0;
        height: calc(100% - 108px);
        font-weight: bold;
    }
    @media(max-width: 600px){
        .jumbo{
            height: 256px;
        }
    }
</style>