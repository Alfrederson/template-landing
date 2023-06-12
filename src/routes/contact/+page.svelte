<script>
    /**
     * @typedef {Object} ContactAnswer
     * @property {string} name    - nome no formulário
     * @property {string} email   - email da pessoa
     * @property {string} message - email da pessoa
    */
    const URL = import.meta.env.VITE_CONTACT_FORM_URL
    const
        WAITING = 0,
        SENDING = 1,
        SENT = 2

    let state = WAITING
    const form = {
        name   :"",
        email  :"",
        message:""
    }

    function sendContact(){
        fetch("URL",{
            method : 'POST',
            headers: {
                "Content-Type" : "application/json",
                body : JSON.stringify(form),
                redirect: "follow"
            }
        })
    }
</script>

<div class="w-full max-w-xl mx-auto min-h-screen">


<form on:submit|preventDefault={sendContact}>
    <div class="w-full form-control p-3">
        <input type="text" class="input form-control input-bordered" bind:value={form.name} placeholder="Name"/>
    </div>  
    <div class="w-full form-control p-3">
        <input type="text" class="input  input-bordered" bind:value={form.email} placeholder="E-mail"/>
    </div>
    <div class="w-full form-control p-3">
        <textarea class="textarea textarea-bordered w-full" bind:value={form.message} placeholder="Write us a message"/>
    </div>
    <div class="p-3">
        <label class="label cursor-pointer justify-start">
            <input type="checkbox" class="checkbox" />
            <span class="label-text mx-3">By checking this box, I agree to receiving a response in my e-mail.</span> 
        </label>
    </div>
    <div class="w-full form-control p-3">
        <input type="submit" class="btn btn-secondary"/>
    </div>
</form>

</div>