<script>
    /**
     * @typedef {Object} ContactAnswer
     * @property {string} name    - nome no formulário
     * @property {string} email   - email da pessoa
     * @property {string} message - email da pessoa
    */
    const URL = import.meta.env.VITE_CONTACT_FORM_URL

    let busy = false, error = "", success = false
    const form = {
        name   :"",
        email  :"",
        message:""
    }

    async function sendContact(){
        if(busy)
            return;
        busy = true
        let result = await fetch(URL,{
            method : 'POST',
            headers: {
                "Content-Type" : "application/json",
            },
            body : JSON.stringify(form),
            redirect: "follow"
        })
        if(result.status !== 200){
            let errorObj = await result.json()
            error = errorObj.err ?? "Something went wrong. Try again later."
            busy = false
            return
        }
        success = true        
        busy = false
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