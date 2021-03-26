<script>
    import { fade, fly } from 'svelte/transition'

    let t, elm
    let showupload, showdelete, showoverlay
    function showUpload(){
        showupload = !showupload
        showoverlay = !showoverlay 
    }
    let fn
    function showDelete(z){
        showdelete = !showdelete
        showoverlay = !showoverlay
        fn = z
    }
    function exedel(e){
        t = e.target
        t.innerHTML = "deleting..."
        let data = {
            filename: fn
        }
        fetch('/delete-file', {
            method: "POST",
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(data)
        }).then(r => r.json()).then(res => {
            t.innerHTML = "Yes"
            if(res.status == "failed"){
                alert(res.message)
                return false
            }
            closeall()
            filedata = getdata()
        })   
    }
    function closeall(){
        showupload = (showupload ? !showupload:showupload)
        showdelete = (showdelete ? !showdelete:showdelete)
        showoverlay = false 
    }

    function setTime(int){
        let time = new Date(int * 1000)
        return `${("0" + time.getDate()).slice(-2)}-${("0" + time.getMonth() + 1).slice(-2)}-${time.getFullYear()} ${("0" + time.getHours()).slice(-2)}:${("0" + time.getMinutes()).slice(-2)}`
    }

    function uploadFiles(e){
        t = e.target
        t.querySelector("button").innerHTML =
        `
        <svg width="24" height="24" viewBox="0 0 120 30" xmlns="http://www.w3.org/2000/svg" fill="currentColor">
            <circle cx="15" cy="15" r="15">
                <animate attributeName="r" from="15" to="15"
                        begin="0s" dur="0.8s"
                        values="15;9;15" calcMode="linear"
                        repeatCount="indefinite" />
                <animate attributeName="fill-opacity" from="1" to="1"
                        begin="0s" dur="0.8s"
                        values="1;.5;1" calcMode="linear"
                        repeatCount="indefinite" />
            </circle>
            <circle cx="60" cy="15" r="9" fill-opacity="0.3">
                <animate attributeName="r" from="9" to="9"
                        begin="0s" dur="0.8s"
                        values="9;15;9" calcMode="linear"
                        repeatCount="indefinite" />
                <animate attributeName="fill-opacity" from="0.5" to="0.5"
                        begin="0s" dur="0.8s"
                        values=".5;1;.5" calcMode="linear"
                        repeatCount="indefinite" />
            </circle>
            <circle cx="105" cy="15" r="15">
                <animate attributeName="r" from="15" to="15"
                        begin="0s" dur="0.8s"
                        values="15;9;15" calcMode="linear"
                        repeatCount="indefinite" />
                <animate attributeName="fill-opacity" from="1" to="1"
                        begin="0s" dur="0.8s"
                        values="1;.5;1" calcMode="linear"
                        repeatCount="indefinite" />
            </circle>
        </svg>
        `
        let data = new FormData();
        let files = []
        elm = t.querySelector("input")
        for(let i = 0; i < elm.files.length; i++){
            files[i] = elm.files[i];
        }
        for(let i = 0; i < files.length; i++){
            data.append('files[]', files[i]);
        }
        fetch('/upload-files', {
            method: "POST",
            body: data
        }).then(r => r.json()).then(res => {
            t.querySelector("button").innerHTML =
            `
            <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                <path fill="currentColor" d="M9,16V10H5L12,3L19,10H15V16H9M5,20V18H19V20H5Z" />
            </svg>
            `
            if(res.status == "failed"){
                alert(res.message)
                return false
            }
            closeall()
            filedata = getdata()
        })
    }

    async function getdata(){
        const res = await fetch('/all-files', { method: "POST" })
        const data = await res.json()
        return data
    }
    let filedata = getdata()

</script>

<svelte:head>
    <title>Dashboard - File Manager</title>
</svelte:head>

<div class="header row middle-xs between-xs">
    <h1>File Manager</h1>
    <button class="row middle-xs" on:click={showUpload}>
        <svg style="width:24px;height:24px" viewBox="0 0 24 24">
            <path fill="currentColor" d="M9,16V10H5L12,3L19,10H15V16H9M5,20V18H19V20H5Z" />
        </svg>
        Upload Files
    </button>
</div>
{#if showdelete}
<div class="pop" in:fly={{ y: 100 }} out:fly={{ y: 100 }}>
    <p style="margin:0 0 12px 0">Delete this file ?</p>
    <button on:click={e => exedel(e)}>Yes</button><button on:click={closeall}>no</button>
</div>
{/if}
{#if showupload}
<div class="pop" in:fly={{ y: 100 }} out:fly={{ y: 100 }}>
    <h3>Upload Your File</h3>
    <form class="row middle-xs" on:submit|preventDefault={e => uploadFiles(e)}>
        <input type="file" name="files" multiple class="col-xs">
        <button type="submit" class="row middle-xs center-xs">
            <svg style="width:24px;height:24px" viewBox="0 0 24 24">
                <path fill="currentColor" d="M9,16V10H5L12,3L19,10H15V16H9M5,20V18H19V20H5Z" />
            </svg>
        </button>
    </form>
</div>
{/if}
{#if showoverlay}
<div class="overlay" on:click={closeall} transition:fade></div>
{/if}
<div class="files row">
    {#await filedata}
    <div class="no-files" style="margin-top: calc(50vh - 116px)">
        Loading...
    </div>
    {:then data}
    {#if data.data.length == 0}
    <div class="no-files" style="margin-top: calc(50vh - 116px)">
        <svg style="width:54px;height:54px" viewBox="0 0 24 24">
            <path fill="currentColor" d="M13 14H11V9H13M13 18H11V16H13M1 21H23L12 2L1 21Z" />
        </svg>
        <br>
        No file, upload your first file
    </div>
    {:else}
    {#each data.data as file}
    <div class="box col-lg-4 col-md-4 col-sm-12 col-xs-12">
        <div class="file">
            <b><a href="/files/{file.name}">{file.name}</a></b><br><br>
            <span class="meta">{setTime(file.created_at)}</span>
            <button on:click={() => showDelete(file.name)}>Delete</button>
        </div>
    </div>
    {/each}
    {/if}
    {:catch err}
    <div class="no-files" style="margin-top: calc(50vh - 116px)">
        {err.message}
    </div>
    {/await}
</div>

<style>
    h1{
        margin: 0;
        font-size: 32px;
        line-height: 40px;
    }
    @media(max-width: 600px){
        h1{
            font-size: 24px;
            line-height: 32px;
        }
    }
    .header{
        margin: 0;
    }
    .header button{
        background: #0065a8;
        color: #fff;
        padding: 4px 6px;
        border: 1px solid #0065a8;
        border-radius: 4px;
        cursor: pointer;
        transition: background .3s, color .3s;
        margin: 0;
    }
    .header button:hover{
        background: #fff;
        color: #0065a8;
    }
    .files{
        padding: 12px 0;
        position: relative;
        margin: -8px -.5rem 0 -.5rem;
    }
    .no-files, .pop{
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
    .pop{
        width: calc(100% - 64px);
        max-width: 300px;
        position: fixed;
        z-index: 99;
        background: #fff;
        padding: 16px;
        border: 1px solid #ddd;
    }
    .pop form{
        margin: 0;
    }
    .pop h3{
        margin: 0 0 12px 0;
    }
    .pop input{
        padding: 8px 12px;
        border: 1px solid #ddd
    }
    .pop button{
        padding: 8px;
        min-width: 60px;
        color: #fff;
        background: #0065a8;
        border: 1px solid #0065a8;
        cursor: pointer;
        transition: background .3s, color .3s;
        margin: 0;
    }
    .pop button:hover{
        background: #fff;
        color: #0065a8;
    }
    .pop button+button{
        background: #fff;
        border: 0;
        color: #444;
        margin-left: 6px;
    }
    .overlay{
        position: fixed;
        top: 0;right: 0;bottom: 0;left: 0;
        background: rgba(0,0,0,.4);
        z-index: 9;
    }
    .files > .box{
        padding: 8px
    }
    .file{
        position: relative;
        padding: 8px 8px 14px 8px;
        border: 1px solid #ddd;
        color: #777;
    }
    .file a{
        overflow-wrap: break-word;
    }
    .file button{
        background: #e74c3c;
        color: #fff;
        padding: 8px;
        border: 1px solid #e74c3c;
        border-radius: 4px;
        position: absolute;
        cursor: pointer;
        right: 8px;bottom: 8px;
        transition: background .3s, color .3s;
    }
    .file button:hover{
        background: #fff;color: #e74c3c;
    }
</style>