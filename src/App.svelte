<script>
	import { Router, links, Route } from "svelte-routing"

	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte'
	import Chat from './components/Chat.svelte'

	import Home from './pages/Home.svelte'
	import Products from './pages/products/Home.svelte'
	import P1 from './pages/products/P1.svelte'
	import P2 from './pages/products/P2.svelte'
	import P3 from './pages/products/P3.svelte'
	import P4 from './pages/products/P4.svelte'
	import P5 from './pages/products/P5.svelte'
	import P6 from './pages/products/P6.svelte'
	import P7 from './pages/products/P7.svelte'
	import P8 from './pages/products/P8.svelte'
	import Solutions from './pages/solutions/Home.svelte'
	import Services from './pages/services/Home.svelte'
	import ManageServices from './pages/services/Manage.svelte'
	import ProfessionalServices from './pages/services/Professional.svelte'
	import CaseStudies from './pages/case-studies/Home.svelte'
	import CS1 from './pages/case-studies/CS1.svelte'
	import CS2 from './pages/case-studies/CS2.svelte'
	import CS3 from './pages/case-studies/CS3.svelte'
	import CS4 from './pages/case-studies/CS4.svelte'
	import CS5 from './pages/case-studies/CS5.svelte'
	import Contact from './pages/Contact.svelte'
	import Blog from './pages/blog/Home.svelte'
	import About from './pages/About.svelte'
	
	import Dashboard from "./pages/dashboard/Home.svelte"
	import Post from "./pages/dashboard/posts/Home.svelte"
	import CreatePost from "./pages/dashboard/posts/Create.svelte"
	import UpdatePost from "./pages/dashboard/posts/Update.svelte"
	import FileManager from "./pages/dashboard/file-manager/Home.svelte"

	import Login from  './pages/dashboard/Login.svelte'

	export let url = ""

	let link = location.pathname
	function detectUrl(){
		requestAnimationFrame(()=>{
			if(link != location.pathname){
				link = location.pathname;
				window.scrollTo(0,0)
			}
        });
	}
	window.onpopstate = () => {
		link = location.pathname
	}

	let checkLogin = async () => {
		if(link.indexOf("/dashboard") == -1){
			return false
		}
		const f = await fetch(`${host}/check-login`, { method: "POST" })
		const r = await f.json()
		if(r.status == "failed"){
			location.assign('/login')
		}
		return r
	}

	$: if(link.indexOf("/dashboard") > -1){
		checkLogin()
	}

	let appWidth = 0

	let menu, menuBtn, menuWidth, sh
	let showMenu = () => {
		sh = !sh
		if(sh){
			menuBtn.style.left = (menuWidth - 1) + "px"
			menu.style.left = 0;
		} else {
			menuBtn.style.left = "0"
			menu.style.left = "-300px";
		}

	}
	
	let closeMenu = () => {
		if(sh && appWidth <= 756){
			sh = !sh
			menuBtn.style.left = "0"
			menu.style.left = "-300px";
		}
	}

	window.addEventListener("resize", () => {
		if(link.indexOf('/dashboard') > -1){
			if(appWidth > 756){
				sh = false
				showMenu()
			} else if(appWidth <= 756) {
				sh = true
				showMenu()
			}
		}
	})
</script>

<div id="app" on:click={detectUrl} bind:offsetWidth="{appWidth}">
	<Header currurl={link} />
	<Router url="{url}">
		<Route path="*"><div class="row middle-xs center-xs" style="height: calc(100vh - 72px);margin: 0">Halaman Tidak Ditemukan</div></Route>
		<Route path="/"><Home /></Route>
		<Route path="/products"><Products /></Route>
		<Route path="/products/uhf-rfid-integrated-reader"><P1 /></Route>
		<Route path="/products/uhf-rfid-fixed-reader"><P2 /></Route>
		<Route path="/products/uhf-rfid-antenna"><P3 /></Route>
		<Route path="/products/uhf-rfid-tag"><P4 /></Route>
		<Route path="/products/uhf-rfid-handheld-reader"><P5 /></Route>
		<Route path="/products/uhf-rfid-desktop-reader"><P6 /></Route>
		<Route path="/products/uhf-rfid-printer"><P7 /></Route>
		<Route path="/products/2-45g-active-rfid"><P8 /></Route>
		<Route path="/solutions"><Solutions /></Route>
		<Route path="/services"><Services /></Route>
		<Route path="/services/manage-services"><ManageServices /></Route>
		<Route path="/services/professional-services"><ProfessionalServices /></Route>
		<Route path="/case-studies"><CaseStudies /></Route>
		<Route path="/case-studies/rfid-for-stock-monitoring"><CS1 /></Route>
		<Route path="/case-studies/rfid-for-faster-inbound-outbound-cashier-process"><CS2 /></Route>
		<Route path="/case-studies/rfid-for-asset-tracking-employee"><CS3 /></Route>
		<Route path="/case-studies/rfid-for-pallet-tracking"><CS4 /></Route>
		<Route path="/case-studies/rfid-for-attendance-tracking-employee-student"><CS5 /></Route>
		<Route path="/contact"><Contact /></Route>
		<Route path="/blog"><Blog /></Route>
		<Route path="/about"><About /></Route>
		{#await checkLogin()}
		<span style="display:block;text-align:center;width: calc(100% - 32px);position: absolute;top: 50%;left: 50%;transform: translate(-50%, -50%);background:#fff;">Loading...</span>
		{:then isLogin}
		{#if isLogin.status == "success" && link.indexOf("/dashboard") > -1}
		<div class="dashboard row">
			<div class="menu" bind:this="{menu}" bind:offsetWidth="{menuWidth}">
				<a href="/dashboard" use:links on:click="{closeMenu}" class="row middle-xs" style="{(link == "/dashboard" || link == "/dashboard/" ? 'color:#0065a8':'')}">
					<svg style="width:22px;height:22px;margin-right:3px" viewBox="0 0 24 24">
						<path fill="currentColor" d="M10,20V14H14V20H19V12H22L12,3L2,12H5V20H10Z" />
					</svg>
					Welcome
				</a>
				<a href="/dashboard/post" use:links on:click="{closeMenu}" class="row middle-xs" style="{(link.indexOf("/dashboard/post") > -1 || link.indexOf("/dashboard/create-post") > -1 || link.indexOf("/dashboard/update-post") > -1 ? 'color:#0065a8':'')}">
					<svg style="width:18px;height:18px;margin-right:5px" viewBox="0 0 24 24">
						<path fill="currentColor" d="M3 3V21H21V3H3M18 18H6V17H18V18M18 16H6V15H18V16M18 12H6V6H18V12Z" />
					</svg>
					Manage Posts
				</a>
				<a href="/dashboard/file-manager" use:links on:click="{closeMenu}" class="row middle-xs" style="{(link.indexOf("/dashboard/file-manager") > -1 ? 'color:#0065a8':'')}">
					<svg style="width:18px;height:18px;margin-right:6px" viewBox="0 0 24 24">
						<path fill="currentColor" d="M7,15L11.5,9L15,13.5L17.5,10.5L21,15M22,4H14L12,2H6A2,2 0 0,0 4,4V16A2,2 0 0,0 6,18H22A2,2 0 0,0 24,16V6A2,2 0 0,0 22,4M2,6H0V11H0V20A2,2 0 0,0 2,22H20V20H2V6Z" />
					</svg>
					File Manager
				</a>
			</div>
			<button bind:this="{menuBtn}" class="mid-mobile row middle-xs center-xs" on:click={showMenu}>
				<svg style="width:32px;height:32px;pointer-events:none" viewBox="0 0 24 24">
					<path fill="currentColor" d="M12,16A2,2 0 0,1 14,18A2,2 0 0,1 12,20A2,2 0 0,1 10,18A2,2 0 0,1 12,16M12,10A2,2 0 0,1 14,12A2,2 0 0,1 12,14A2,2 0 0,1 10,12A2,2 0 0,1 12,10M12,4A2,2 0 0,1 14,6A2,2 0 0,1 12,8A2,2 0 0,1 10,6A2,2 0 0,1 12,4Z" />
				</svg>
			</button>
			<div class="right col-sm col-xs-12">
				<Route path="/dashboard"><Dashboard /></Route>
				<Route path="/dashboard/post"><Post /></Route>
				<Route path="/dashboard/create-post"><CreatePost /></Route>
				<Route path="/dashboard/update-post/:link" let:params><UpdatePost plink="{params.link}" /></Route>
				<Route path="/dashboard/file-manager"><FileManager /></Route>
			</div>
		</div>
		{:else}
		<Route path="/login"><Login /></Route>
		{/if}
		{/await}	
		<Route path="/login"><Login /></Route>
	</Router>
	{#if link.indexOf('/dashboard') == -1}
	<Chat />
	<Footer />
	{/if}
</div>

<style>
	#app{
		min-height: 100vh;
	}
	.dashboard{
		height: calc(100vh - 72px);
		width: 100%;
		max-width: 1328px;
		margin: 0 auto;
	}
	.dashboard .menu{
		position: relative;
		left: 0;
		width: 50%;
		max-width: 300px;
		background: #fff;
		box-sizing: border-box;
		border-right: 1px solid #ddd;
		border-left: 1px solid #ddd;
		height: calc(100vh - 72px);
		margin-left: -1px;
	}
	.dashboard .menu a{
		padding: 12px 16px;
		border-bottom: 1px solid #ddd;
		color: #444;
		transition: color .3s;
		margin: 0;
	}
	.dashboard .menu a:hover{
		color: #0065a8;
	}
	.mid-mobile{
		display: none;
		background: #fff;
		border: 1px solid #ddd;
		margin: 0;
		border-radius: 0 100% 100% 0;
		padding: 16px 16px 16px 8px;
		transition: left .3s;
		cursor: pointer;
	}
	@media(max-width: 756px){
		.dashboard .menu{
			position: fixed!important;z-index: 999;
			top: 73px;
			left: -300px;
			transition: left .3s;
		}
		.mid-mobile{
			display: flex;
			position: absolute;z-index: 99;
			bottom: 16px;
			left: 0;
		}
	}
	.dashboard .right{
        padding: 12px 16px 16px 16px;
        position: relative;
        height: calc(100vh - 80px);
        overflow: auto;
	}
</style>