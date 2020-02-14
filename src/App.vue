<template>
    <div id="app">
        <header id="header_content">
            <h1>Alfian --dev</h1>
        </header>
        <main>
            <p id="message">
                <i>
                    Dynamic Component with
                    <br />Vue.js using &lt;keep-alive&gt; and &lt;component&gt;
                </i>
            </p>
            <div id="button_section">
                <button id="signup_btn" @click="comp = 'form-signup'">Sign Up</button>
                <button id="login_btn" @click="comp = 'form-login'">Login</button>
            </div>
            <div id="form_section">
                <!-- <keep-alive> to make component still alive, because dynamic component make component destroyed -->
                <keep-alive>
                    <!-- attribute 'is' and value refer to the component -->
                    <component :is="comp"></component>
                </keep-alive>
            </div>
        </main>
        <footer></footer>
    </div>
</template>

<script>
import SignUp from "./components/SignUp.vue";
import Login from "./components/Login.vue";

export default {
    data() {
        return {
            comp: "form-signup"
        };
    },
    components: {
        "form-signup": SignUp,
        "form-login": Login
    }
};
</script>

<style>
</style>