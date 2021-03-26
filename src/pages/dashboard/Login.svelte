<script>
    let alertbox, email, password, btn;
    function goLogin(){
        alertbox.innerText = ""
        btn.innerHTML = 
        `
        <svg width="44" height="32" viewBox="0 0 120 30" xmlns="http://www.w3.org/2000/svg" fill="currentColor">
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
        let data = {
            email, password
        }
        fetch('/login', {
            method: "POST",
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(data)
        }).then(r => r.json()).then(res => {
            if(res.status == "success"){
                location.assign("/dashboard")
            } else {
                alertbox.innerText = res.message + "    !!!"
                btn.innerText = "Login"
            }
        })
    }
</script>

<svelte:head>
    <title>RFID Solutions - Login</title>
</svelte:head>

<div class="login row middle-xs center-xs">
    <div class="box">
        <img src="/favicon.png" alt="M2Fleet" style="width: 86px;height: 80px;" />
        <form on:submit|preventDefault="{goLogin}">
            <div class="alert" bind:this="{alertbox}"></div>
            <input type="email" name="email" autocomplete="off" placeholder="Email" bind:value="{email}">
            <input type="password" name="password" autocomplete="off" placeholder="Password" bind:value="{password}">
            <button type="submit" bind:this="{btn}">Login</button>
        </form>
    </div>
</div>

<style>
    .login{
        position: absolute;
        top: 0;right: 0;bottom: 0;left: 0;
        background: #0065a8;
        margin: 0;
    }
    .login .box{
        background: #fff;
        padding: 16px;
        border-radius: 8px;
        width: calc(100% - 64px);
        max-width: 400px;
        box-shadow: 0 2px 4px rgba(0,0,0,.2);
    }
    form{
        text-align: center;
    }
    input, button{
        margin-top: 12px;
    }
    input{
        padding: 8px 12px;
        border: 1px solid #ddd;
        border-radius: 6px;
        width: calc(100% - 26px);   
        transition: border .3s;
        color: #555;
    }
    input:focus{
        border: 1px solid #0065a8;
    }
    button{
        display: inline-block;
        background: #0065a8;
        color: #fff;
        height: 37px;
        width: 100px;
        border-radius: 6px;
        border: 1px solid #0065a8;
        cursor: pointer;
        transition: background .3s, color .3s;
    }
    button:hover{
        background: #fff;
        color: #0065a8;
    }
    .alert{
        color: #e74c3c;
        margin-top: 2px;
    }
</style>