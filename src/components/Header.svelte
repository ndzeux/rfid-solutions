<script>
    import { link } from 'svelte-routing'

    export let currurl

    let headerWidth

    let showproducts, showsolutions, showservices, showindustries, showcasestudies
    let t, elm, elm2, ml, st, cc
    function showSubMenu(e, y, z) {
        if(headerWidth <= 1200){
            return false
        }
        if(e){
            t = e.target
        }
        elm = t.parentNode.querySelector(".popmenu")
        if(y){
            clearTimeout(st)
            showproducts = showsolutions = showservices = showindustries = showcasestudies = false
            if(z == 'pr'){
                showproducts = true
                ml = -50
            } else if(z == 'sl'){
                showsolutions = true
                ml = 54
            } else if(z == 'sr'){
                showservices = true
                ml = 224
            } else if(z == 'in'){
                showindustries = true
                ml = 332
            } else if(z == 'cs'){
                showcasestudies = true
                ml = 350
            }
            if(elm.style.top == ""){
                elm.style.cssText = "display:block;left:" + ml + "px;"
                setTimeout(()=>{
                    elm.style.opacity = "1"
                    elm.style.top = "88px"
                }, 100)
            } else {
                elm.style.cssText = "display:block;left:" + ml + "px;top:88px;opacity:1"
            }
        } else {
            elm.style.opacity = ""
            elm.style.top = "72px"
            st = setTimeout(()=>{
                showproducts = showsolutions = showservices = showindustries = showcasestudies = false
                elm.style.cssText = "display:none"
            }, 300)
        }
    }
    function showSubMenu2(z){
        if(showproducts){
            showSubMenu(false, z, 'pr')
        } else if(showsolutions){
            showSubMenu(false, z, 'sl')
        } else if(showservices){
            showSubMenu(false, z, 'sr')
        } else if(showindustries){
            showSubMenu(false, z, 'in')
        } else if(showcasestudies){
            showSubMenu(false, z, 'cs')
        }
    }
    let oomdclick
    function showMenuMobile(e){
        if(cc){
            return false
        }
        t = e.target || t
        t.classList.toggle("open")
        oomdclick = !oomdclick
        elm = document.querySelector(".popmenu.formobile")
        elm2 = elm.parentNode.querySelector(".arrows.formobile")
        cc = true
        if(elm.style.display == "none"){
            elm2.style.display = ""
            elm.style.cssText = "display:block;right:16px;"
            setTimeout(()=>{
                elm2.style.cssText = "left:auto;right:24px;"
                elm2.style.opacity = "1"
                elm2.style.top = "65px"
                setTimeout(()=>{
                    elm2.style.transition = "top .3s, opacity .2s"
                    cc = false
                }, 100)
                elm.style.opacity = "1"
                elm.style.top = "88px"
            }, 100)
        } else {
            elm2.style.opacity = ""
            elm2.style.top = ""
            elm.style.opacity = ""
            elm.style.top = "67px"
            st = setTimeout(()=>{
                showproducts = showsolutions = showservices = showindustries = showcasestudies = false
                elm.style.cssText = "display:none"
                elm2.style.cssText = "display:none"
                cc = false
            }, 300)
        }
    }
    let submenumobile
    function showSubMenu3(e, z){
        if(cc){
            return false
        }
        t = e.target
        elm = t.parentNode.parentNode
        elm2 = t.querySelector("svg")
        submenumobile = [elm.querySelector(".productssubmenu"), elm.querySelector(".solutionssubmenu"), elm.querySelector(".servicessubmenu"), elm.querySelector(".industriessubmenu"), elm.querySelector(".casestudiessubmenu")]
        cc = true
        if(elm2.style.transform == "rotate(0deg)"){
            submenumobile.forEach(smm => smm.style.maxHeight = "")
            elm.querySelectorAll("button svg").forEach(s => s.style.transform = "rotate(0)")
            elm2.style.transform = "rotate(-180deg)"
            if(z == 'pr'){
                submenumobile[0].style.maxHeight = "343px"
            } else if(z == 'sl'){
                submenumobile[1].style.maxHeight = "161px"
            } else if(z == 'sr'){
                submenumobile[2].style.maxHeight = "98px"
            } else if(z == 'in'){
                submenumobile[3].style.maxHeight = "392px"
            } else if(z == 'cs'){
                submenumobile[4].style.maxHeight = "365px"
            }
            cc = false
        } else {
            elm2.style.transform = "rotate(0)"
            if(z == 'pr'){
                submenumobile[0].style.maxHeight = ""
            } else if(z == 'sl'){
                submenumobile[1].style.maxHeight = ""
            } else if(z == 'sr'){
                submenumobile[2].style.maxHeight = ""
            } else if(z == 'in'){
                submenumobile[3].style.maxHeight = ""
            } else if(z == 'cs'){
                submenumobile[4].style.maxHeight = ""
            }
            cc = false
        }
    }
    let scrolly = window.scrollY
    window.addEventListener('scroll', () => {
        scrolly = window.scrollY
    })
    window.addEventListener('resize', () => {
        if(headerWidth > 1200 || headerWidth <= 1200){
            showproducts = showsolutions = showservices = showindustries = showcasestudies = false
            if(oomdclick && headerWidth > 1200){
                oomdclick = false
                t.classList.toggle('open')
            }
        }
    })

    let tempUrl = currurl;
    $: if(currurl != tempUrl && headerWidth <= 1200 && oomdclick){
        showMenuMobile(document.querySelector(".open-menu-mobile"));
        tempUrl = currurl;
    }

</script>

<header class="row middle-xs" bind:clientWidth={headerWidth} style="{(currurl == '/' && scrolly <= 25 ? 'background:linear-gradient(to bottom, rgb(0, 0, 0, .8), rgba(0, 0, 0, 0.5), rgb(0, 0, 0, .2), rgba(0,0,0,0));box-shadow:none':'')}">
    <div class="container row middle-xs between-xs">
        <div class="logo row middle-xs">
            <a use:link href="/" class="row middle-xs" style="margin:0">
                <img src="{(currurl == "/" && scrolly <= 25 ? '/src/img/rfid-solutions-logo-white.png':'/src/img/rfid-solutions-logo.png')}" alt="Logo">
            </a>
        </div>
        {#if headerWidth > 1200}
        <div class="menu for-desktop row middle-xs {(currurl == '/' && scrolly <= 25 ?  'whitechild':'')}">
            <a use:link style="{(currurl.indexOf('/products') > -1 ? 'color:#006588':'')}" href="/products" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'pr')} on:mouseout="{e => showSubMenu(e, false, 'pr')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M21,16.5C21,16.88 20.79,17.21 20.47,17.38L12.57,21.82C12.41,21.94 12.21,22 12,22C11.79,22 11.59,21.94 11.43,21.82L3.53,17.38C3.21,17.21 3,16.88 3,16.5V7.5C3,7.12 3.21,6.79 3.53,6.62L11.43,2.18C11.59,2.06 11.79,2 12,2C12.21,2 12.41,2.06 12.57,2.18L20.47,6.62C20.79,6.79 21,7.12 21,7.5V16.5M12,4.15L10.11,5.22L16,8.61L17.96,7.5L12,4.15M6.04,7.5L12,10.85L13.96,9.75L8.08,6.35L6.04,7.5M5,15.91L11,19.29V12.58L5,9.21V15.91M19,15.91V9.21L13,12.58V19.29L19,15.91Z"></path>
                </svg>
                Products
            </a>
            <a use:link style="{(currurl.indexOf('/solutions') > -1 ? 'color:#006588':'')}" href="/solutions" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'sl')} on:mouseout="{e => showSubMenu(e, false, 'sl')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M20,11H23V13H20V11M1,11H4V13H1V11M13,1V4H11V1H13M4.92,3.5L7.05,5.64L5.63,7.05L3.5,4.93L4.92,3.5M16.95,5.63L19.07,3.5L20.5,4.93L18.37,7.05L16.95,5.63M12,6A6,6 0 0,1 18,12C18,14.22 16.79,16.16 15,17.2V19A1,1 0 0,1 14,20H10A1,1 0 0,1 9,19V17.2C7.21,16.16 6,14.22 6,12A6,6 0 0,1 12,6M14,21V22A1,1 0 0,1 13,23H11A1,1 0 0,1 10,22V21H14M11,18H13V15.87C14.73,15.43 16,13.86 16,12A4,4 0 0,0 12,8A4,4 0 0,0 8,12C8,13.86 9.27,15.43 11,15.87V18Z"></path>
                </svg>
                Solutions
            </a>
            <a use:link style="{(currurl.indexOf('/services') > -1 ? 'color:#006588':'')}" href="/services" class="row middle-xs">
                <!--  on:mouseover={e => showSubMenu(e, true, 'sr')} on:mouseout="{e => showSubMenu(e, false, 'sr')}" -->
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M18.72,14.76C19.07,13.91 19.26,13 19.26,12C19.26,11.28 19.15,10.59 18.96,9.95C18.31,10.1 17.63,10.18 16.92,10.18C13.86,10.18 11.15,8.67 9.5,6.34C8.61,8.5 6.91,10.26 4.77,11.22C4.73,11.47 4.73,11.74 4.73,12A7.27,7.27 0 0,0 12,19.27C13.05,19.27 14.06,19.04 14.97,18.63C15.54,19.72 15.8,20.26 15.78,20.26C14.14,20.81 12.87,21.08 12,21.08C9.58,21.08 7.27,20.13 5.57,18.42C4.53,17.38 3.76,16.11 3.33,14.73H2V10.18H3.09C3.93,6.04 7.6,2.92 12,2.92C14.4,2.92 16.71,3.87 18.42,5.58C19.69,6.84 20.54,8.45 20.89,10.18H22V14.67H22V14.69L22,14.73H21.94L18.38,18L13.08,17.4V15.73H17.91L18.72,14.76M9.27,11.77C9.57,11.77 9.86,11.89 10.07,12.11C10.28,12.32 10.4,12.61 10.4,12.91C10.4,13.21 10.28,13.5 10.07,13.71C9.86,13.92 9.57,14.04 9.27,14.04C8.64,14.04 8.13,13.54 8.13,12.91C8.13,12.28 8.64,11.77 9.27,11.77M14.72,11.77C15.35,11.77 15.85,12.28 15.85,12.91C15.85,13.54 15.35,14.04 14.72,14.04C14.09,14.04 13.58,13.54 13.58,12.91A1.14,1.14 0 0,1 14.72,11.77Z"></path>
                </svg>
                Services
            </a>
            <a use:link style="{(currurl.indexOf('/industries') > -1 ? 'color:#006588':'')}" href="/" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'in')} on:mouseout="{e => showSubMenu(e, false, 'in')}">
                <svg style="width:20px;height:16px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M19 3V21H13V17.5H11V21H5V3H19M15 7H17V5H15V7M11 7H13V5H11V7M7 7H9V5H7V7M15 11H17V9H15V11M11 11H13V9H11V11M7 11H9V9H7V11M15 15H17V13H15V15M11 15H13V13H11V15M7 15H9V13H7V15M15 19H17V17H15V19M7 19H9V17H7V19M21 1H3V23H21V1Z"></path>
                </svg>
                Industries
            </a>
            <a use:link style="{(currurl.indexOf('/case-studies') > -1 ? 'color:#006588':'')}" href="/case-studies" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'cs')} on:mouseout="{e => showSubMenu(e, false, 'cs')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M20,6C20.58,6 21.05,6.2 21.42,6.59C21.8,7 22,7.45 22,8V19C22,19.55 21.8,20 21.42,20.41C21.05,20.8 20.58,21 20,21H4C3.42,21 2.95,20.8 2.58,20.41C2.2,20 2,19.55 2,19V8C2,7.45 2.2,7 2.58,6.59C2.95,6.2 3.42,6 4,6H8V4C8,3.42 8.2,2.95 8.58,2.58C8.95,2.2 9.42,2 10,2H14C14.58,2 15.05,2.2 15.42,2.58C15.8,2.95 16,3.42 16,4V6H20M4,8V19H20V8H4M14,6V4H10V6H14M12,9A2.25,2.25 0 0,1 14.25,11.25C14.25,12.5 13.24,13.5 12,13.5A2.25,2.25 0 0,1 9.75,11.25C9.75,10 10.76,9 12,9M16.5,18H7.5V16.88C7.5,15.63 9.5,14.63 12,14.63C14.5,14.63 16.5,15.63 16.5,16.88V18Z"></path>
                </svg>
                Case Studies
            </a>
            <a use:link style="{(currurl.indexOf('/contact') > -1 ? 'color:#006588':'')}" href="/contact" class="row middle-xs">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M22 6C22 4.9 21.1 4 20 4H4C2.9 4 2 4.9 2 6V18C2 19.1 2.9 20 4 20H20C21.1 20 22 19.1 22 18V6M20 6L12 11L4 6H20M20 18H4V8L12 13L20 8V18Z"></path>
                </svg>
                Contact
            </a>
            <a use:link style="{(currurl.indexOf('/blog') > -1 ? 'color:#006588':'')}" href="/blog" class="row middle-xs">
                <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M19 5V19H5V5H19M21 3H3V21H21V3M17 17H7V16H17V17M17 15H7V14H17V15M17 12H7V7H17V12Z" />
                </svg>
                Blog
            </a>
            <a use:link style="{(currurl.indexOf('/about') > -1 ? 'color:#006588':'')}" href="/about" class="row middle-xs">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M11,9H13V7H11M12,20C7.59,20 4,16.41 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,16.41 16.41,20 12,20M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M11,17H13V11H11V17Z"></path>
                </svg>
                About
            </a>
            <div class="popmenu" style="display:none" on:mouseover={() => showSubMenu2(true)} on:mouseout={() => showSubMenu2(false)}>
                <div class="arrows"><div class="arrow"></div></div>
                {#if showproducts}
                <a use:link href="/products/uhf-rfid-integrated-reader">UHF RFID Integrated Reader</a>
                <a use:link href="/products/uhf-rfid-fixed-reader">UHF RFID Fixed Reader</a>
                <a use:link href="/products/uhf-rfid-antenna">UHF RFID Antenna</a>
                <a use:link href="/products/uhf-rfid-tag">UHF RFID Tag</a>
                <a use:link href="/products/uhf-rfid-handheld-reader">UHF RFID Handheld Reader</a>
                <a use:link href="/products/uhf-rfid-desktop-reader">UHF RFID Dekstop Reader</a>
                <a use:link href="/products/uhf-rfid-printer">UHF RFID Printer</a>
                <a use:link href="/products/2-45g-active-rfid">2.45G Active RFID</a>
                {:else if showsolutions}
                <a use:link href="/solutions/warehouse-inventory-monitoring">Warehouse Inventory Monitoring</a>
                <a use:link href="/solutions/attendance-tracking">Attendance Tracking</a>
                <a use:link href="/solutions/asset-tracking">Asset Tracking</a>
                {:else if showservices}
                <a use:link href="/services/managed-services">Managed Services</a>
                <a use:link href="/services/professional-services">Professional Services</a>
                {:else if showindustries}
                <a use:link href="/industries/construction">Construction</a>
                <a use:link href="/industries/distribution">Distribution</a>
                <a use:link href="/industries/healthcare">Healthcare</a>
                <a use:link href="/industries/manufacturing">Manufacturing</a>
                <a use:link href="/industries/media-&amp;-communication">Media &amp; Communication</a>
                <a use:link href="/industries/oil-&amp;-gas">Oil &amp; Gas</a>
                <a use:link href="/industries/transportation-&amp;-logistics">Transportation &amp; Logistics</a>
                <a use:link href="/industries/utilities">Utilities</a>
                {:else if showcasestudies}
                <a use:link href="/case-studies/rfid-for-stock-monitoring">Case : RFID for Stock Monitoring</a>
                <a use:link href="/case-studies/rfid-for-faster-inbound-outbound-cashier-process">Case : RFID for faster Inbound, Outbound, Cashier Process</a>
                <a use:link href="/case-studies/rfid-for-asset-tracking-employee">Case : RFID for Asset Tracking (Employee)</a>
                <a use:link href="/case-studies/rfid-for-pallet-tracking">Case : RFID for Pallet Tracking</a>
                <a use:link href="/case-studies/rfid-for-attendance-tracking-employee-student">Case : RFID for Attendance Tracking (Employee,Student)</a>
                {/if}
            </div>
        </div>
        {:else}
        <button class="open-menu-mobile row middle-xs {(currurl == "/" && scrolly <= 25 ? (oomdclick ? 'whitechild open':'whitechild'):(oomdclick ? 'open':''))}" on:click={e => showMenuMobile(e)}>
            <span></span>
            <span></span>
            <span></span>
            <span></span>
        </button>
        <div class="arrows formobile" style="display:none"><div class="arrow"></div></div>
        <div class="popmenu formobile" style="display:none">
            <a use:link href="/products" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'pr')} on:mouseout="{e => showSubMenu(e, false, 'pr')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M21,16.5C21,16.88 20.79,17.21 20.47,17.38L12.57,21.82C12.41,21.94 12.21,22 12,22C11.79,22 11.59,21.94 11.43,21.82L3.53,17.38C3.21,17.21 3,16.88 3,16.5V7.5C3,7.12 3.21,6.79 3.53,6.62L11.43,2.18C11.59,2.06 11.79,2 12,2C12.21,2 12.41,2.06 12.57,2.18L20.47,6.62C20.79,6.79 21,7.12 21,7.5V16.5M12,4.15L10.11,5.22L16,8.61L17.96,7.5L12,4.15M6.04,7.5L12,10.85L13.96,9.75L8.08,6.35L6.04,7.5M5,15.91L11,19.29V12.58L5,9.21V15.91M19,15.91V9.21L13,12.58V19.29L19,15.91Z"></path>
                </svg>
                Products
                <button class="row middle-xs center-xs" on:click|preventDefault={e => showSubMenu3(e, 'pr')}>
                    <svg style="width:28px;height:28px;pointer-events:none;transform:rotate(0);transition:transform .3s" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                    </svg>
                </button>
            </a>
            <div class="productssubmenu">
                <a use:link href="/products/uhf-rfid-integrated-reader" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Integrated Reader
                </a>
                <a use:link href="/products/uhf-rfid-fixed-reader" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Fixed Reader
                </a>
                <a use:link href="/products/uhf-rfid-antenna" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Antenna
                </a>
                <a use:link href="/products/uhf-rfid-tag" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Tag
                </a>
                <a use:link href="/products/uhf-rfid-handheld-reader" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Handheld Reader
                </a>
                <a use:link href="/products/uhf-rfid-desktop-reader" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Dekstop Reader
                </a>
                <a use:link href="/products/uhf-rfid-printer" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    UHF RFID Printer
                </a>
                <a use:link href="/products/2-45g-active-rfid" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    2.45G Active RFID
                </a>
            </div>
            <a use:link href="/solutions" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'sl')} on:mouseout="{e => showSubMenu(e, false, 'sl')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M20,11H23V13H20V11M1,11H4V13H1V11M13,1V4H11V1H13M4.92,3.5L7.05,5.64L5.63,7.05L3.5,4.93L4.92,3.5M16.95,5.63L19.07,3.5L20.5,4.93L18.37,7.05L16.95,5.63M12,6A6,6 0 0,1 18,12C18,14.22 16.79,16.16 15,17.2V19A1,1 0 0,1 14,20H10A1,1 0 0,1 9,19V17.2C7.21,16.16 6,14.22 6,12A6,6 0 0,1 12,6M14,21V22A1,1 0 0,1 13,23H11A1,1 0 0,1 10,22V21H14M11,18H13V15.87C14.73,15.43 16,13.86 16,12A4,4 0 0,0 12,8A4,4 0 0,0 8,12C8,13.86 9.27,15.43 11,15.87V18Z"></path>
                </svg>
                Solutions
                <button class="row middle-xs center-xs" on:click|preventDefault={e => showSubMenu3(e, 'sl')}>
                    <svg style="width:28px;height:28px;pointer-events:none;transform:rotate(0);transition:transform .3s" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                    </svg>
                </button>
            </a>
            <div class="solutionssubmenu">
                <a use:link href="/solutions/warehouse-inventory-monitoring" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Warehouse Inventory Monitoring
                </a>
                <a use:link href="/solutions/attendance-tracking" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Attendance Tracking
                </a>
                <a use:link href="/solutions/asset-tracking" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Asset Tracking
                </a>
            </div>
            <a use:link href="/services" class="row middle-xs">
                <!--  on:mouseover={e => showSubMenu(e, true, 'sr')} on:mouseout="{e => showSubMenu(e, false, 'sr')}" -->
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M18.72,14.76C19.07,13.91 19.26,13 19.26,12C19.26,11.28 19.15,10.59 18.96,9.95C18.31,10.1 17.63,10.18 16.92,10.18C13.86,10.18 11.15,8.67 9.5,6.34C8.61,8.5 6.91,10.26 4.77,11.22C4.73,11.47 4.73,11.74 4.73,12A7.27,7.27 0 0,0 12,19.27C13.05,19.27 14.06,19.04 14.97,18.63C15.54,19.72 15.8,20.26 15.78,20.26C14.14,20.81 12.87,21.08 12,21.08C9.58,21.08 7.27,20.13 5.57,18.42C4.53,17.38 3.76,16.11 3.33,14.73H2V10.18H3.09C3.93,6.04 7.6,2.92 12,2.92C14.4,2.92 16.71,3.87 18.42,5.58C19.69,6.84 20.54,8.45 20.89,10.18H22V14.67H22V14.69L22,14.73H21.94L18.38,18L13.08,17.4V15.73H17.91L18.72,14.76M9.27,11.77C9.57,11.77 9.86,11.89 10.07,12.11C10.28,12.32 10.4,12.61 10.4,12.91C10.4,13.21 10.28,13.5 10.07,13.71C9.86,13.92 9.57,14.04 9.27,14.04C8.64,14.04 8.13,13.54 8.13,12.91C8.13,12.28 8.64,11.77 9.27,11.77M14.72,11.77C15.35,11.77 15.85,12.28 15.85,12.91C15.85,13.54 15.35,14.04 14.72,14.04C14.09,14.04 13.58,13.54 13.58,12.91A1.14,1.14 0 0,1 14.72,11.77Z"></path>
                </svg>
                Services
                <!-- <button class="row middle-xs center-xs" on:click|preventDefault={e => showSubMenu3(e, 'sr')}>
                    <svg style="width:28px;height:28px;pointer-events:none;transform:rotate(0);transition:transform .3s" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                    </svg>
                </button> -->
            </a>
            <!-- <div class="servicessubmenu">
                <a use:link href="/service/managed-services" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Managed Services
                </a>
                <a use:link href="/professional-services" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Professional Services
                </a>
            </div> -->
            <a use:link href="/" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'in')} on:mouseout="{e => showSubMenu(e, false, 'in')}">
                <svg style="width:20px;height:16px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M19 3V21H13V17.5H11V21H5V3H19M15 7H17V5H15V7M11 7H13V5H11V7M7 7H9V5H7V7M15 11H17V9H15V11M11 11H13V9H11V11M7 11H9V9H7V11M15 15H17V13H15V15M11 15H13V13H11V15M7 15H9V13H7V15M15 19H17V17H15V19M7 19H9V17H7V19M21 1H3V23H21V1Z"></path>
                </svg>
                Industries
                <button class="row middle-xs center-xs" on:click|preventDefault={e => showSubMenu3(e, 'in')}>
                    <svg style="width:28px;height:28px;pointer-events:none;transform:rotate(0);transition:transform .3s" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                    </svg>
                </button>
            </a>
            <div class="industriessubmenu">
                <a use:link href="/industries/construction" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Construction
                </a>
                <a use:link href="/industries/distribution" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Distribution
                </a>
                <a use:link href="/industries/healthcare" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Healthcare
                </a>
                <a use:link href="/industries/manufacturing" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Manufacturing
                </a>
                <a use:link href="/industries/media-&amp;-communication" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Media &amp; Communication
                </a>
                <a use:link href="/industries/oil-&amp;-gas" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Oil &amp; Gas
                </a>
                <a use:link href="/industries/transportation-&amp;-logistics" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Transportation &amp; Logistics
                </a>
                <a use:link href="/industries/utilities" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Utilities
                </a>
            </div>
            <a use:link href="/case-studies" class="row middle-xs" on:mouseover={e => showSubMenu(e, true, 'cs')} on:mouseout="{e => showSubMenu(e, false, 'cs')}">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M20,6C20.58,6 21.05,6.2 21.42,6.59C21.8,7 22,7.45 22,8V19C22,19.55 21.8,20 21.42,20.41C21.05,20.8 20.58,21 20,21H4C3.42,21 2.95,20.8 2.58,20.41C2.2,20 2,19.55 2,19V8C2,7.45 2.2,7 2.58,6.59C2.95,6.2 3.42,6 4,6H8V4C8,3.42 8.2,2.95 8.58,2.58C8.95,2.2 9.42,2 10,2H14C14.58,2 15.05,2.2 15.42,2.58C15.8,2.95 16,3.42 16,4V6H20M4,8V19H20V8H4M14,6V4H10V6H14M12,9A2.25,2.25 0 0,1 14.25,11.25C14.25,12.5 13.24,13.5 12,13.5A2.25,2.25 0 0,1 9.75,11.25C9.75,10 10.76,9 12,9M16.5,18H7.5V16.88C7.5,15.63 9.5,14.63 12,14.63C14.5,14.63 16.5,15.63 16.5,16.88V18Z"></path>
                </svg>
                Case Studies
                <button class="row middle-xs center-xs" on:click|preventDefault={e => showSubMenu3(e, 'cs')}>
                    <svg style="width:28px;height:28px;pointer-events:none;transform:rotate(0);transition:transform .3s" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z" />
                    </svg>
                </button>
            </a>
            <div class="casestudiessubmenu">
                <a use:link href="/case-studies/rfid-for-stock-monitoring" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Case : RFID for Stock Monitoring
                </a>
                <a use:link href="/case-studies/rfid-for-faster-inbound-outbound-cashier-process" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Case : RFID for faster Inbound, Outbound, Cashier Process
                </a>
                <a use:link href="/case-studies/rfid-for-asset-tracking-employee" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Case : RFID for Asset Tracking (Employee)
                </a>
                <a use:link href="/case-studies/rfid-for-pallet-tracking" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Case : RFID for Pallet Tracking
                </a>
                <a use:link href="/case-studies/rfid-for-attendance-tracking-employee-student" class="row middle-xs">
                    <svg style="width:20px;min-width:20px;height:20px;margin-right: 5px" viewBox="0 0 24 24">
                        <path fill="currentColor" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
                    </svg>
                    Case : RFID for Attendance Tracking (Employee,Student)
                </a>
            </div>
            <a use:link href="/contact" class="row middle-xs">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M22 6C22 4.9 21.1 4 20 4H4C2.9 4 2 4.9 2 6V18C2 19.1 2.9 20 4 20H20C21.1 20 22 19.1 22 18V6M20 6L12 11L4 6H20M20 18H4V8L12 13L20 8V18Z"></path>
                </svg>
                Contact
            </a>
            <a use:link href="/blog" class="row middle-xs">
                <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M19 5V19H5V5H19M21 3H3V21H21V3M17 17H7V16H17V17M17 15H7V14H17V15M17 12H7V7H17V12Z" />
                </svg>
                Blog
            </a>
            <a use:link href="/about" class="row middle-xs">
                <svg style="width:20px;height:20px" viewBox="0 0 24 24">
                    <path fill="currentColor" d="M11,9H13V7H11M12,20C7.59,20 4,16.41 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,16.41 16.41,20 12,20M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M11,17H13V11H11V17Z"></path>
                </svg>
                About
            </a>
        </div>
        {/if}
    </div>
</header>

<style>
    header{
        position: sticky;z-index: 3;
        top: 0;
        background: #fff;
        height: 72px;
        box-shadow: 0 2px 4px rgba(0,0,0,.075);
        margin: 0;
        transition: background .3s;
    }
    .container{
        width: 100%;
        max-width: 1360px;
        margin: 0 auto;
        padding: 0 16px;
    }
    header .logo{
        width: 180px;
        margin: 0;
    }
    header .logo img{
        width: 100%;height: auto;
    }
    header .menu{
        position: relative;
        margin: 0;
    }
    header .menu > a{
        color: #444;
        height: 72px;
        padding: 0 24px;
        transition: color .3s;
    }
    header .menu > a:hover{
        color: #0065a8;
    }
    header .menu a svg{
        pointer-events: none;
        margin-right: 4px;
    }
    .popmenu{
        position: absolute;
        top: 80px;
        background: #0065a8;
        padding: 0;
        opacity: 0;
        box-shadow: 0 2px 4px rgba(0,0,0, .4);
        transition: top .3s, left .7s, opacity .3s;
    }
    .popmenu::after{
        position: absolute;
        top: -15px;
        content: '';
        left: 0;
        right: 0;
        height: 15px;
        background: rgba(0,0,0,0);
    }
    .popmenu a{
        background: #0065a8;
        height: auto;
        display: block;
        padding: 12px;
        color: #fff;
        border-bottom: 1px solid #005a96;
        transition: background .3s;
    }
    .popmenu a:hover{
        background: #005a96;
    }
    .arrows{
        position: absolute;
        content: '';
        left: calc(50% - 11px);
        top: -24px;
        border-left: 12px solid transparent;
        border-right: 12px solid transparent;
        border-bottom: 12px solid #0000001f;
        border-top: 12px solid transparent;
    }
    .arrow{
        position: absolute;
        left: calc(50% - 10px);
        top: -8px;
        border-left: 10px solid transparent;
        border-right: 10px solid transparent;
        border-bottom: 10px solid #0065a8;
        border-top: 10px solid transparent;
    }
    .arrows.formobile{
        top: 52px;
        opacity: 0;
        transition: top .18s, opacity .2s;
    }
    .arrows.formobile .arrow{
        top: -9 px;
    }
    .popmenu.formobile{
        width: calc(100% - 32px);
        max-width: 400px;
        max-height: calc(100vh - 104px);
        overflow: auto;
    }
    .popmenu.formobile > div{
        max-height: 0;
        overflow: hidden;
        transition: max-height .3s
    }
    .popmenu.formobile a{
        display: flex;
        flex-wrap: nowrap;
        margin: 0;
    }
    .popmenu.formobile a > svg{
        margin-right: 5px;
    }
    .popmenu.formobile > a button {
        margin: 0;
        position: absolute;
        right: 12px;
        background: rgba(0,0,0,0);
        border: 0;
        color: #fff;
        cursor: pointer;
    }
    .open-menu-mobile {
        background: rgba(0,0,0,0);
        border: 0;
        width: 36px;
        height: 24px;
        margin: 0 0 -4px 0;
        position: relative;
        flex-direction: column;
        -webkit-transform: rotate(0deg);
        -moz-transform: rotate(0deg);
        -o-transform: rotate(0deg);
        transform: rotate(0deg);
        -webkit-transition: .5s ease-in-out;
        -moz-transition: .5s ease-in-out;
        -o-transition: .5s ease-in-out;
        transition: .5s ease-in-out;
        cursor: pointer;
    }
    .open-menu-mobile span {
        pointer-events: none;
        display: block;
        position: absolute;
        height: 4px;
        width: 100%;
        background: #444;
        border-radius: 1px;
        opacity: 1;
        left: 0;
        -webkit-transform: rotate(0deg);
        -moz-transform: rotate(0deg);
        -o-transform: rotate(0deg);
        transform: rotate(0deg);
        -webkit-transition: .25s ease-in-out;
        -moz-transition: .25s ease-in-out;
        -o-transition: .25s ease-in-out;
        transition: .25s ease-in-out;
    }
    .whitechild > a{
        color: #fff!important;
    }
    .whitechild > a:hover{
        color: #43b4ff!important;
    }
    .whitechild > span{
        background: #fff;
    }
    .open-menu-mobile span:nth-child(1) {
        top: 0px;
    }

    .open-menu-mobile span:nth-child(2),.open-menu-mobile span:nth-child(3) {
        top: 10px;
    }

    .open-menu-mobile span:nth-child(4) {
        top: 20px;
    }
</style>