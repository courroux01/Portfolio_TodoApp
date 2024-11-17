<script>
    let email = "";
    let password = "";
    let confirmPassword = "";
    let error = false;
    let register = false;

    function handleAuthenticate() {
        if(
            !email || 
            !password || 
            (register && !confirmPassword)
        ) {
            error = true;
            return;
        }
    }

    function handleRegister() {
        register = !register;
    }

    function handleLogin(){}
</script>

<div class="authContainer">
    <form>
        <h1>{register ? "Register" : "Login"}</h1>

        {#if error}
        <p class="error">
            Incorrect information input.
        </p>
        {/if}

        <label>
            <p class={email ? "above" : "center"}>Email</p>
            <input 
                bind:value={email} 
                type="email" 
                placeholder="Email" 
                required
            />
        </label>
        <label>
            <p class={password ? "above" : "center"}>Password</p>
            <input 
                bind:value={password} 
                type="password" 
                placeholder="Password"
                required
            />
        </label>
        <label>
            <p class={confirmPassword ? "above" : "center"}>Confirm Password</p>
            <input 
                bind:value={confirmPassword} 
                type="password" 
                placeholder="Confirm Password" 
                required
            />
        </label>
        <button type="submit">Submit</button>
    </form>

    <div class='options'>
        <p>Or</p>
        {#if register}
            <div>
                <p>Already have an account?</p>
                <button
                    on:click={handleRegister}
                    on:keydown={()=>{}}
                > Login
                </button>
            </div>
        {:else}
            <div>
                <p>Don't have an account?</p>
                <button
                    on:click={handleRegister}
                    on:keydown={()=>{}}
                > Register
                </button>
            </div>
        {/if}
    </div>
</div>

<style>
    .authContainer {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        flex: 1;
    }

    h1 {
        text-align: center;
    }

    form {
        display: flex;
        flex-direction: column;
        gap: 8px;
    }

    form, .options {
        width: 400px;
        max-width: 100%;
        gap: 14px;
        position: relative;
    }

    form input {
        width: 100%;
        border: none;
        background: transparent;
        color: white;
        padding: 8px 16px;
    }

    form input:focus {
        border: none;
        outline: none;
    }
    
    form label:focus-within {
        border-color: blue;
    }

    form label {
        position: relative;
        border: 1px solid navy;
        border-radius: 5px;
        padding: 5px 0;
    }

    form label:focus {
        border: none;
        outline: none;
    }
    
    form button {
        background: navy;
        color: white;
        border: none;
        padding: 10px 0;
        border-radius: 5px;
        cursor: pointer;
        text-transform: uppercase;
        font-size: 1rem;
    }

    form button:hover {
        background: blue;
    }

    .above,
    .center {
        position: absolute;
        transform: translateY(-50%);
        pointer-events: none;
        color: white;
        border-radius: 5px;
        padding: 0 6px;
        font-size: 0.8rem;
        transition: all 0.2s ease-in-out;
    }

    .above {
        top: 0;
        left: 24px;
        background: navy;
        border: 1px solid blue;
        font-size: 0.7rem;
    }

    .center {
        top: 50%;
        left: 6px;
        opacity: 0; 
        border: 1px solid transparent;
    }

    .error {
        color: coral;
        font-size: 0.9rem;
    }

    .options {
        padding: 14px 0;
        overflow: hidden;
        font-size: 0.9rem;
    }

    .options > p {
        position: relative;
        text-align: center;
        width: fit-content;
        margin: 0 auto;
        padding: 0 8px;

    }

    .options > p::before,
    .options > p::after {
        position: absolute;
        content: '';
        top: 50%;
        transform: translateY(-50%);
        width: 100vw;
        height: 1.5px;
        background: white;
    }

    .options > p::after {
        right: 100%;
    }

    .options > p::before {
        left: 100%;
    }

    .options div {
        display: flex;
        width: 100%;
        border: 1px solid black;
        align-items: center;
        justify-content: space-between;
    }

    .options div button {
        border: none;
        background: none;
        color: blue; 
        cursor: pointer;
    }

</style>
