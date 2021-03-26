<script>
    let f = true, t, tb, st1, st2, st3, nc
    function showChatBox(e){
        t = e.target
        tb = t.parentNode.querySelector(".chat-box")
        if(nc){
            return
        }
        nc = true
        if(f){
            clearTimeout(st2)
            clearTimeout(st3)
            f = !f
            tb.style.display = ""
            st1 = setTimeout(()=>{
                tb.style.width = "72%"
                tb.style.height = "314px"
                t.style.cssText = "border-radius: 0 100% 100% 100%;background: #075E54"
                nc = false
            }, 1)
            t.querySelector("svg path").setAttribute("d", "M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z")
        } else {
            clearTimeout(st1)
            tb.style.height = "4px"
            st2 = setTimeout(()=>{
                tb.style.width = ""
            }, 500)
            st3 = setTimeout(()=>{
                tb.style.cssText = "display:none"
                t.querySelector("svg path").setAttribute("d", "M12.04 2C6.58 2 2.13 6.45 2.13 11.91C2.13 13.66 2.59 15.36 3.45 16.86L2.05 22L7.3 20.62C8.75 21.41 10.38 21.83 12.04 21.83C17.5 21.83 21.95 17.38 21.95 11.92C21.95 9.27 20.92 6.78 19.05 4.91C17.18 3.03 14.69 2 12.04 2M12.05 3.67C14.25 3.67 16.31 4.53 17.87 6.09C19.42 7.65 20.28 9.72 20.28 11.92C20.28 16.46 16.58 20.15 12.04 20.15C10.56 20.15 9.11 19.76 7.85 19L7.55 18.83L4.43 19.65L5.26 16.61L5.06 16.29C4.24 15 3.8 13.47 3.8 11.91C3.81 7.37 7.5 3.67 12.05 3.67M8.53 7.33C8.37 7.33 8.1 7.39 7.87 7.64C7.65 7.89 7 8.5 7 9.71C7 10.93 7.89 12.1 8 12.27C8.14 12.44 9.76 14.94 12.25 16C12.84 16.27 13.3 16.42 13.66 16.53C14.25 16.72 14.79 16.69 15.22 16.63C15.7 16.56 16.68 16.03 16.89 15.45C17.1 14.87 17.1 14.38 17.04 14.27C16.97 14.17 16.81 14.11 16.56 14C16.31 13.86 15.09 13.26 14.87 13.18C14.64 13.1 14.5 13.06 14.31 13.3C14.15 13.55 13.67 14.11 13.53 14.27C13.38 14.44 13.24 14.46 13 14.34C12.74 14.21 11.94 13.95 11 13.11C10.26 12.45 9.77 11.64 9.62 11.39C9.5 11.15 9.61 11 9.73 10.89C9.84 10.78 10 10.6 10.1 10.45C10.23 10.31 10.27 10.2 10.35 10.04C10.43 9.87 10.39 9.73 10.33 9.61C10.27 9.5 9.77 8.26 9.56 7.77C9.36 7.29 9.16 7.35 9 7.34C8.86 7.34 8.7 7.33 8.53 7.33Z")
                t.style.cssText = ""
                f = !f
                nc = false
            }, 1000)
        }
    }
    let chatWithSales = () => {
        if(window.innerWidth > 600){
            window.open("https://web.whatsapp.com/send?phone=%27+628111751214&text=")
        } else {
            window.open("https://wa.me/628111751214?text=")
        }
    }
</script>

<button class="chat-btn row middle-xs" title="Whatsapp Chat" on:click={e => showChatBox(e)}>
    <svg viewBox="0 0 24 24" style="width: 36px;height: 36  px;pointer-events:none">
        <path fill="#fff" d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91C2.13 13.66 2.59 15.36 3.45 16.86L2.05 22L7.3 20.62C8.75 21.41 10.38 21.83 12.04 21.83C17.5 21.83 21.95 17.38 21.95 11.92C21.95 9.27 20.92 6.78 19.05 4.91C17.18 3.03 14.69 2 12.04 2M12.05 3.67C14.25 3.67 16.31 4.53 17.87 6.09C19.42 7.65 20.28 9.72 20.28 11.92C20.28 16.46 16.58 20.15 12.04 20.15C10.56 20.15 9.11 19.76 7.85 19L7.55 18.83L4.43 19.65L5.26 16.61L5.06 16.29C4.24 15 3.8 13.47 3.8 11.91C3.81 7.37 7.5 3.67 12.05 3.67M8.53 7.33C8.37 7.33 8.1 7.39 7.87 7.64C7.65 7.89 7 8.5 7 9.71C7 10.93 7.89 12.1 8 12.27C8.14 12.44 9.76 14.94 12.25 16C12.84 16.27 13.3 16.42 13.66 16.53C14.25 16.72 14.79 16.69 15.22 16.63C15.7 16.56 16.68 16.03 16.89 15.45C17.1 14.87 17.1 14.38 17.04 14.27C16.97 14.17 16.81 14.11 16.56 14C16.31 13.86 15.09 13.26 14.87 13.18C14.64 13.1 14.5 13.06 14.31 13.3C14.15 13.55 13.67 14.11 13.53 14.27C13.38 14.44 13.24 14.46 13 14.34C12.74 14.21 11.94 13.95 11 13.11C10.26 12.45 9.77 11.64 9.62 11.39C9.5 11.15 9.61 11 9.73 10.89C9.84 10.78 10 10.6 10.1 10.45C10.23 10.31 10.27 10.2 10.35 10.04C10.43 9.87 10.39 9.73 10.33 9.61C10.27 9.5 9.77 8.26 9.56 7.77C9.36 7.29 9.16 7.35 9 7.34C8.86 7.34 8.7 7.33 8.53 7.33Z" />
    </svg>
</button>
<div class="chat-box" style="display: none;">
    <div class="chat-header row middle-xs">
        <div>
            <svg style="width:44px;height:44px;background: #fff;color: #075E54;border-radius: 6px;margin-right: 8px" viewBox="0 0 24 24">
                <path fill="currentColor" d="M18.72,14.76C19.07,13.91 19.26,13 19.26,12C19.26,11.28 19.15,10.59 18.96,9.95C18.31,10.1 17.63,10.18 16.92,10.18C13.86,10.18 11.15,8.67 9.5,6.34C8.61,8.5 6.91,10.26 4.77,11.22C4.73,11.47 4.73,11.74 4.73,12A7.27,7.27 0 0,0 12,19.27C13.05,19.27 14.06,19.04 14.97,18.63C15.54,19.72 15.8,20.26 15.78,20.26C14.14,20.81 12.87,21.08 12,21.08C9.58,21.08 7.27,20.13 5.57,18.42C4.53,17.38 3.76,16.11 3.33,14.73H2V10.18H3.09C3.93,6.04 7.6,2.92 12,2.92C14.4,2.92 16.71,3.87 18.42,5.58C19.69,6.84 20.54,8.45 20.89,10.18H22V14.67H22V14.69L22,14.73H21.94L18.38,18L13.08,17.4V15.73H17.91L18.72,14.76M9.27,11.77C9.57,11.77 9.86,11.89 10.07,12.11C10.28,12.32 10.4,12.61 10.4,12.91C10.4,13.21 10.28,13.5 10.07,13.71C9.86,13.92 9.57,14.04 9.27,14.04C8.64,14.04 8.13,13.54 8.13,12.91C8.13,12.28 8.64,11.77 9.27,11.77M14.72,11.77C15.35,11.77 15.85,12.28 15.85,12.91C15.85,13.54 15.35,14.04 14.72,14.04C14.09,14.04 13.58,13.54 13.58,12.91A1.14,1.14 0 0,1 14.72,11.77Z" />
            </svg>
        </div>
        <div>
            <b>Sales Support</b>
            <span>Text me for detail</span>
        </div>
    </div>
    <div class="chat-area">
        <div class="chat">
            Hi, sir
        </div><br>
        <div class="chat">
            I ready to help you, please text me for free
        </div>
    </div>
    <div class="chat-button row middle-xs center-xs">
        <button class="row middle-xs" on:click="{chatWithSales}">
            <svg viewBox="0 -256 1536 1548" style="width: 22px;height: 22px;pointer-events:none;margin-right: 6px"><path fill="#fff" transform="matrix(1,0,0,-1,0,1158)" d="m 985,562 q 13,0 98,-44 84,-44 89,-53 2,-5 2,-15 0,-33 -17,-76 -16,-39 -71,-65.5 -55,-26.5 -102,-26.5 -57,0 -190,62 -98,45 -170,118 -72,73 -148,185 -72,107 -71,194 v 8 q 3,91 74,158 24,22 52,22 6,0 18,-1 12,-2 19,-2 19,0 26.5,-6 7.5,-7 15.5,-28 8,-20 33,-88 25,-68 25,-75 0,-21 -34.5,-57.5 Q 599,735 599,725 q 0,-7 5,-15 34,-73 102,-137 56,-53 151,-101 12,-7 22,-7 15,0 54,48.5 39,48.5 52,48.5 z M 782,32 q 127,0 244,50 116,50 200,134 84,84 134,200.5 50,116.5 50,243.5 0,127 -50,243.5 -50,116.5 -134,200.5 -84,84 -200,134 -117,50 -244,50 -127,0 -243.5,-50 Q 422,1188 338,1104 254,1020 204,903.5 154,787 154,660 154,457 274,292 L 195,59 437,136 Q 595,32 782,32 z m 0,1382 q 153,0 293,-60 139,-60 240,-161 101,-101 161,-240.5 Q 1536,813 1536,660 1536,507 1476,367.5 1416,228 1315,127 1214,26 1075,-34 935,-94 782,-94 587,-94 417,0 L 0,-134 136,271 Q 28,449 28,660 q 0,153 60,292.5 60,139.5 161,240.5 101,101 240.5,161 139.5,60 292.5,60 z"></path></svg>        
            Chat Me
        </button>
    </div>
</div>

<style>
    .chat-btn{
        background: #25D366;
        border-radius: 100%;
        border: 0;
        position: fixed;
        z-index: 9999999;
        right: 16px;
        bottom: 16px;
        padding: 12px;
        cursor: pointer;
        box-shadow: 0 2px 5px 0 rgba(0,0,0,0.16), 0 2px 10px 0 rgba(0,0,0,0.12);
        border-radius: 100%;
    }
    .chat-box{
        position: fixed;
        z-index: 9999999;
        right: 56px;bottom: 56px;
        background: #fff;
        border: 8px solid #075E54;
        border-radius: 16px;
        width: 0%;height: 0;
        overflow: hidden;
        max-width: 320px;
        transition: width .5s, height .75s;
    }
    .chat-header{
        padding: 8px;
        background: #075E54;
        color: #fff;
    }
    .chat-header b{
        display: block;
        margin-top: -8px;
    }
    .chat-header span{
        display: block;
        font-size: 14px;
        margin-top: -2px;
    }
    .chat-area{
        background: #e4dccc url(/src/img//wa-bg.png) center no-repeat;
        background-size: cover;
        min-height: 162px;
        padding: 8px;
    }
    .chat-area .chat{
        position: relative;
        background: #fff;
        display: inline-block;
        padding: 8px 12px;
        max-width: 60%;
        margin: 0 0 8px 8px;
        border-radius: 0 6px 6px 6px;
    }
    .chat-area .chat::before{
        position: absolute;
        content: '';
        top: 0;left: -8px;
        border-top: 8px solid #fff;
        border-right: 8px solid transparent;
        border-bottom: 8px solid transparent;
        border-left: 8px solid transparent;
    }


    .chat-button{
        text-align: center;
        background: #fff;
        padding: 12px;
        border-radius: 0 0 16px 16px;
    }
    .chat-button button{
        background: #075E54;
        border: 0;
        padding: 12px 16px;
        border-radius: 6px;
        color: #fff;
        font-size: 20px;
        font-weight: bold;
        cursor: pointer;
    }
</style>