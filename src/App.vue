<template>
    <div id="app">
        <div id="nav">
            <router-link v-if="authenticated" to="/login" v-on:click.native="logout()" replace>Logout</router-link>
        </div>
        <router-view @authenticated="setAuthenticated" ql="questionsLookUp"/>
    </div>
</template>

<script>
import questions from '@/assets/quiz_data/questions.json'

const quizData = "https://api.myjson.com/bins/opxdc"
    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
                mockAccount: {
                    username: "blake",
                    password: "password"
                }
            }
        },
        mounted() {

        //     if(!this.authenticated) {
        //         this.$router.replace({ name: "login" });
        //     }
        },
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }
</script>

<style>
    body {
        background-color: #F0F0F0;
    }
    h1 {
        padding: 0;
        margin-top: 0;
    }
    #app {
        width: 1024px;
        margin: auto;
    }
</style>
