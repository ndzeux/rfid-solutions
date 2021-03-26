<script>
    import { fly } from 'svelte/transition'

    export let plink

    let cl
    fetch(`/post/${plink}/admin`, { method: "POST" }).then(r => r.json()).then(res => {
        title = res.data.title
        cl = editor.querySelector(".block").classList[1]
        editor.innerHTML = res.data.body
        description = res.data.description
        cover = res.data.cover
        setTimeout(()=>{
            editor.querySelectorAll(".block").forEach(b => {
                b.setAttribute("contenteditable", "")
                b.classList.add(cl)
            })
        }, 100)
    })

    //

    let editor, coverarea, coverph
    let showalert
    let status, title, cover, description

    let loadCover = () => {
        if(!coverarea.innerText){
            return false
        }
        cover = coverarea.innerText
        coverarea.style.textAlign = "center"
        coverarea.innerHTML = `<img src=${cover} />`
    }
    let resetcover = (e) => {
        if((e.keyCode === 8 || e.keyCode === 46) && coverarea.innerText == ""){
            cover = ""
            coverarea.style.textAlign = "left"
        }
    }
    let coverinput = (e) => {
        if(coverarea.querySelector("img")){
            coverarea.innerText = coverarea.querySelector("img").src
            coverph.style.display = "none"
            loadCover()
            return false
        }
        if(e.target.innerText != ""){
            coverph.style.display = "none"
        } else {
            coverph.style.display = ""
        }
    }


    let optionBeauty = {
        "indent_size": "1",
        "indent_char": "\t",
        "max_preserve_newlines": "0",
        "preserve_newlines": true,
        "keep_array_indentation": false,
        "break_chained_methods": false,
        "indent_scripts": "normal",
        "brace_style": "expand",
        "space_before_conditional": true,
        "unescape_strings": false,
        "jslint_happy": false,
        "end_with_newline": true,
        "wrap_line_length": "0",
        "indent_inner_html": false,
        "comma_first": false,
        "e4x": false,
        "indent_empty_lines": false
    }
    let updatePost = (e) => {
        if(status == "public"){
            e.target.querySelector(".btn button").innerText = "Publishing..."
        } else {
            e.target.querySelector(".btn button+button").innerText = "Saving..."
        }
        let coverimage = () => {
            if(cover){
                return cover
            } else {
                if(editor.querySelector("img")){
                    cover = editor.querySelector("img").src
                } else {
                    cover = '/src/img/no-image.png'
                }
                return cover
            }
        }
        let data = {
            status,
            title,
            body: (editor.innerText == "" ? '':editor.innerHTML.replace(/{br}/g, "<br>").replace(/ contenteditable=""/g, "").replace(new RegExp(" " + editor.querySelector(".block").classList[1], "g"), "")),
            cover: coverimage(),
            description: (description ? description:editor.innerText.substring(0, 200))
        }
        fetch(`/update-post/${plink}`, {
            method: "POST",
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(data)
        }).then(r => r.json()).then(res => {
            if(status == "public"){
                e.target.querySelector(".btn button").innerText = "Publication"
            } else {
                e.target.querySelector(".btn button+button").innerText = "Draft"
            }
            if(res.status == "success"){
                document.querySelector(".menu a+a").click()
            } else {
                showalert = true
                setTimeout(()=>{
                    document.querySelector(".alert span").innerText = res.message
                }, 1)
            }
        })        
    }


    //

    let t, turl, tcol, trow
    let tool = (e, z) => {
        t = editor.querySelector(".block.active-block")
        if(!t){
            return false
        }
        switch(z){
            case 'br':
                t.focus()
                document.execCommand('insertText', false, "{br}");
                break;
            case 'pleft':
                t.style.textAlign = "left"
                t.focus()
                break;
            case 'pcenter':
                t.style.textAlign = "center"
                t.focus()
                break;
            case 'pright':
                t.style.textAlign = "right"
                t.focus()
                break;
            case 'h2':
                t.focus()
                document.execCommand('formatBlock', false, '<h2>')
                break;
            case 'h3':
                t.focus()
                document.execCommand('formatBlock', false, '<h3>')
                break;
            case 'h4':
                t.focus()
                document.execCommand('formatBlock', false, '<h4>')
                break;
            case 'bold':
                // t.focus()
                document.execCommand('bold')
                break;
            case 'italic':
                t.focus()
                document.execCommand('italic')
                break;
            case 'underline':
                t.focus()
                document.execCommand('underline')
                break;
            case 'link':
                t.focus()
                turl = prompt('Enter a url:', 'http:// or https')
                if(document.getSelection()){
                    document.execCommand('insertHTML', false, `<a href="${turl}">${document.getSelection()}</a>`)
                } else {
                    return false
                }
                break;
            case 'ul':
                // t.focus()
                document.execCommand('insertHTML', false, "<ul><li>list</li></ul>");
                break;
            case 'ol':
                t.focus()
                document.execCommand('insertHTML', false, "<ol><li>list</li></ol>");
                break;
            case 'img':
                t.focus()
                turl = prompt('Enter image url:', 'http:// or https')
                let width = prompt('Enter image width', 'auto')
                let height = prompt('Enter image height', 'auto')
                if(!turl){
                    return false
                }
                document.execCommand('insertHTML', false, `<img style="width:${width}px;height:${height}px" src="${turl}" alt="${prompt('Enter image description', 'Just Image')}" />`)
                break;
            case 'video':
                t.focus()
                turl = prompt('Enter video url:', 'http:// or https')
                if(!turl){
                    return false
                }
                document.execCommand('insertHTML', false, `<video style="width: 100%;max-width: 500px" controls><source src="${turl}" type="video/mp4"></video>`)
                break;
            case 'table':
                t.focus()
                tcol = prompt('Enter col:', '1')
                trow = prompt('Enter row:', '1')
                let gentable = () => {
                    let temp = ""
                    for(let i = 0; i < trow; i++){
                        temp += "<tr>"
                        for(let j = 0; j < tcol; j++){
                            temp += "<td>Your table</td>"
                        }
                        temp += "</tr>"
                    }
                    return temp
                }
                document.execCommand('insertHTML', false, `
                <div class="table-box">
                    <table>
                        ${gentable()}
                    </table>
                </div>
                `)
                break;
            default:
                break;
        }
    }
    let activeBlock = (e) => {
        if(e.target.classList[0] == "block"){
            e.target.focus()
            if(editor.querySelector(".block.active-block")){
                editor.querySelector(".block.active-block").classList.remove("active-block");
            }
            e.target.classList.add("active-block");
        }
    }
    let newLineBlock = (e) => {
        if(e.keyCode === 13){
            if(e.target.innerHTML != ""){
                editor.innerHTML +=
                `
                <div class="block ${e.target.classList[1]}" contenteditable></div>
                `
                let a = {}
                a.target = editor.lastElementChild
                activeBlock(a)
                setTimeout(()=>{
                    editor.lastElementChild.innerHTML = ""
                }, 1)
            } else {
                e.preventDefault()
                return false
            }
        } else if(e.keyCode === 8){
            if(editor.querySelectorAll(".block").length > 1 && e.target.innerText == ""){
                e.target.remove()
            }
        }
    }

    function pastehandle(e){
        var text = e.clipboardData.getData('text/plain')
        document.execCommand('insertText', false, text)
    }




</script>

<svelte:head>
    <title>Dashboard - Update Post</title>
    <link rel="stylesheet" href="/post.css">
    <script src="/src/js/beauty-html.js"></script>
</svelte:head>

<form on:submit|preventDefault="{e => updatePost(e)}">
    <div class="inp">
        <input type="text" name="title" autocomplete="off" placeholder="Title" bind:value="{title}" style="font-size:28px">
    </div>
    <div class="toolbar row">
        <button type="button" class="col-xs" on:click={e => tool(e, 'br')}>br</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'pleft')}>pleft</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'pcenter')}>pcenter</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'pright')}>pright</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'h2')}>H2</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'h3')}>H3</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'h4')}>H4</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'bold')}>B</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'italic')}>I</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'underline')}>U</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'link')}>link</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'ul')}>ul</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'ol')}>ol</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'img')}>img</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'video')}>video</button>
        <button type="button" class="col-xs" on:click={e => tool(e, 'table')}>table</button>
    </div>
    <div class="editor" bind:this="{editor}" on:keydown="{e => newLineBlock(e)}" on:click="{e => activeBlock(e)}" on:paste|preventDefault={e => pastehandle(e)}>
        <div class="block"></div>
    </div>
    <span style="display:none" class="ph" bind:this="{coverph}">Image url, will showing as cover</span>
    <div class="input" style="text-align:center" bind:this="{coverarea}" contenteditable on:input="{e => coverinput(e)}" on:focusout="{e => loadCover(e)}" on:keydown="{resetcover}"><img src="{cover}" alt="Cover Article" /></div>
    <div class="inp">
        <input type="text" name="description" autocomplete="off" bind:value="{description}" placeholder="Article description max: 200 characters">
    </div>
    <div class="btn">
        <button type="submit" on:click={() => status = "public"}>Publication</button><button type="submit" on:click={() => status = "draft"}>Draft</button>
    </div>
</form>
{#if showalert}
<div class="alert row middle-xs between-xs" transition:fly={{ y: 40 }}>
    <span>Error</span>
    <button on:click={() => showalert = false}>close</button>
</div>
{/if}

<style>
    .alert{
        position: fixed;
        width: calc(100% - 32px);
        max-width: 400px;
        margin: 0;
        padding: 0 0 0 16px;
        bottom: 16px;
        right: 16px;
        background: #e74c3c;
        color: #fff;
    }
    .alert button{
        background: #c72e1d;
        color: #fff;
        border: 0;
        padding: 16px;
        cursor: pointer;
    }
    input, .input{
        position: relative;
        z-index: 2;
        box-sizing: border-box;
        padding: 12px 0;
        margin-bottom: 12px;
        border: 0;
        border-bottom: 1px solid #ccc;
        width: 100%
    }
    .ph{
        z-index: 1;
        color: #777;
        position: absolute;
        float: left;
        margin-top: 12px;
    }
    .toolbar{
        top: -16px;
        position: sticky;z-index: 3;
        margin: 0;
        margin-bottom: 8px
    }
    .toolbar button{
        width: 100%;
        max-width: 100px;
        padding: 8px 16px;
        border: 1px solid #ddd
    }
    .block {
        border: 1px solid #efefef;
        border-radius: 12px;
        padding: 12px 8px;
        margin-bottom: 8px
    }
    .btn{
        padding: 12px 0;
    }
    .btn button{
        background: #0065a8;
        padding: 12px 16px;
        color: #fff;
        border: 1px solid #0065a8;
        cursor: pointer;
        margin-right: 12px;
        transition: background .3s, color .3s;
    }
    .btn button:hover{
        background: #fff;
        color: #0065a8;
    }
</style>