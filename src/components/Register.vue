<script>

import axios from 'axios';
import {useRouter} from 'vue-router';

export default {
    data() {
        return {
            name: '',
            email: '',
            password: '',
            password_confirmation: '',
            error: '',
            router: useRouter()
        };
    },
    methods: {
        async register() {
            try {
                const response = await axios.post('http://localhost:8000/api/register', {
                    name: this.name,
                    email: this.email,
                    password: this.password,
                    password_confirmation: this.password_confirmation
                });
                console.log(response.data);
                this.router.push('/');
            } catch (error) {
                this.error = error.response.data.message;
            }
        }
    }
};
</script>

<template>
    <div class="container">
        <div class="register">
            <h2>Register</h2>
            <form @submit.prevent="register">
                <div>
                    <label for="name">Name:</label>
                    <input type="text" v-model="name" required />
                </div>
                <div>
                    <label for="email">Email:</label>
                    <input type="email" v-model="email" required />
                </div>
                <div>
                    <label for="password">Password:</label>
                    <input type="password" v-model="password" required />
                </div>
                <div>
                    <label for="password_confirmation">Confirm Password:</label>
                    <input type="password" v-model="password_confirmation" required />
                </div>
                <div class="button">
                    <button type="submit">Register</button>
                </div>
            </form>
            <div v-if="error" class="error">{{ error }}</div>
        </div>
    </div>
</template>



<style scoped lang="scss">
    .container {
    display: flex;
    justify-content: center;
    height: 80vh;
    align-items: center;


    .register{
        background-color: white;
        padding: 40px;
        border-radius: 10px;
        width: 50%;
        height: fit-content;

        h2{
            text-align: center;
            color: rgb(51, 89, 161);
            margin: 10px 0;
        }

        label{
            color: black;
            text-align: start;
        }

        input{
            padding: 5px 0 ;
            margin: 10px 5px;
            width: 100%;
            border-radius: 5px;
            border: 1px solid black;
        }

        .button{
            text-align: center;

            button{
                padding: 10px 20px;
                border-radius: 5px;
                width: 50%;
                background-color: #007bff;
                color: white;
                font-weight: bold;
                border: none;
                transition: 1s ease-in-out;
                cursor: pointer;
                margin: 10px 0;
                
            }
        }
    }
}
</style>