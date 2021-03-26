<script>
    let captcha
    function generateCaptcha(){
        let result = ''
        let characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789'
        for (let i = 0;i < 6;i++){
            result += characters.charAt(Math.floor(Math.random() * characters.length))
        }
        captcha = result
        return result
    }
    let data;
    let sendMsg = () => {

    }
</script>

<div class="contact">
    <h1>Contact</h1>
    If you have business inquiries or other questions, please fill out the following form to contact us. Thank you.
    <form on:submit|preventDefault="{sendMsg}">
        <div class="inp">
            <label for="name">Name</label>
            <input type="text" name="name" autocomplete="off">
        </div>
        <div class="inp">
            <label for="email">Email</label>
            <input type="email" name="email" autocomplete="off">
        </div>
        <div class="inp">
            <label for="subject">Subject</label>
            <input type="text" name="subject" autocomplete="off">
        </div>
        <div class="inp">
            <label for="text">Text</label>
            <textarea name="text" rows="10"></textarea>
        </div>
        <div class="inp">
            <span class="captcha">{generateCaptcha()}</span>
            <input type="text" name="name" autocomplete="off" placeholder="captcha">
        </div>
        <div class="btn">
            <button type="submit">Send</button>
        </div>
    </form>
</div>

<style>
    .contact{
        width: calc(100% - 32px);
        max-width: 1328px;
        margin: 0 auto;
        padding: 16px;
    }
    .contact h1{
        margin: 0;
    }
    .inp{
        margin-top: 8px;
    }
    .inp label, .inp .captcha{
        display: block;
        margin-bottom: 4px;
    }
    .inp input{
        display: block;
        padding: 8px 12px;
        border: 1px solid #ddd;
        transition: border .3s;
    }
    .inp textarea{
        width: calc(100% - 24px);
        max-width: 500px;
        display: block;
        padding: 8px 12px;
        border: 1px solid #ddd;
        resize: none;
        transition: border .3s;
    }
    .inp input:focus, .inp textarea:focus{
        border: 1px solid #006588
    }
    .inp .captcha{
        display: inline-block;
        background: #222;
        padding: 8px 12px;
        color: #fff;
        font-size: 28px;
    }
    .btn{
        margin: 16px 0;
    }
    .btn button{
        padding: 8px 0;
        width: 100px;
        background: #006688;
        color: #fff;
        border: 1px solid #006688;
        cursor: pointer;
        transition: background .3s, color .3s;
    }
    .btn button:hover{
        color: #006588;
        background: #fff;
    }
</style>