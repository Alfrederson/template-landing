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
        success=false
        error  =""
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
            try{
                let errorObj = await result.json()
                error = errorObj.err ?? "Something went wrong. Try again later."
            }catch(e){
                console.log(e)
            }
            busy = false
            return
        }
        success = true        
        busy = false
    }
</script>

<div class="w-full max-w-xl mx-auto min-h-screen">
    {#if error}
        <div class="alert w-full justify-center bg-error p-3 mx-auto">
            {error}
        </div>
    {/if}
    {#if success}
        <div class="alert w-full justify-center bg-success p-3 mx-auto">
            <h1>Your message was received!</h1>
        </div>
    {/if}
    {#if !success}
        <form on:submit|preventDefault={sendContact}>
            <fieldset disabled={busy}>
                <div class="w-full form-control p-3">
                    <input type="text" class="input form-control input-bordered" required bind:value={form.name} placeholder="Name"/>
                </div>  
                <div class="w-full form-control p-3">
                    <input type="text" class="input  input-bordered" required bind:value={form.email} placeholder="E-mail"/>
                </div>
                <div class="w-full form-control p-3">
                    <textarea class="textarea textarea-bordered w-full" required bind:value={form.message} placeholder="Write us a message"/>
                </div>
                <div class="p-3">
                    <label class="label cursor-pointer justify-start">
                        <input type="checkbox" class="checkbox" required/>
                        <span class="label-text mx-3">By checking this box, I agree to receiving a response in my e-mail.</span> 
                    </label>
                </div>
                <div class="w-full form-control p-3">
                    <input type="submit" class="btn btn-secondary"/>
                </div>
            </fieldset>
        </form>
    {/if}
</div>