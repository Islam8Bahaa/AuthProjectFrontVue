<!-- <script>
import { onMounted } from 'vue';
import axios from 'axios';
import { useRouter } from 'vue-router';

export default {

    data() {
        return {
            router : useRouter(),
            isAuthenticated : false,
        }
    },
    mounted(){
        checkAuth();
    },
    methods: {
        checkAuth(){
            const token = localStorage.getItem('token');
            isAuthenticated.value = !!token;
        },
        async logout(){
            try {
                const token = localStorage.getItem('token');
                await axios.post(
                    'http://127.0.0.1:8000/api/logout',
                    {},
                    {
                        headers: {
                            Authorization: `Bearer ${token}`,
                        },
                    }
                );
                localStorage.removeItem('token');
                localStorage.removeItem('userName');
                isAuthenticated.value = false;
                router.push('/');
            } catch (error) {
                console.error('Logout error:', error);
            }
            return { isAuthenticated, logout };
        }
    }

};
</script> -->


<script>
import axios from 'axios';
import { useRouter } from 'vue-router';

export default {
    data() {
        return {
            isAuthenticated: false,
        };
    },
    mounted() {
        this.checkAuth();
    },
    methods: {
        checkAuth() {
            const token = localStorage.getItem('token');
            this.isAuthenticated = !!token;
        },
        async logout() {
            try {
                const token = localStorage.getItem('token');
                await axios.post(
                    'http://127.0.0.1:8000/api/logout',
                    {},
                    {
                        headers: {
                            Authorization: `Bearer ${token}`,
                        },
                    }
                );
                localStorage.removeItem('token');
                localStorage.removeItem('userName');
                this.isAuthenticated = false;
                this.$router.push('/');
            } catch (error) {
                console.error('Logout error:', error);
            }
        },
    },
};
</script>

<template>
    <nav class="navbar">
        <router-link to="/" class="navbar-brand">My App</router-link>
        <div class="navbar-nav">
            
            <router-link to="/" class="nav-item" v-if="!isAuthenticated">Login</router-link>
            <router-link to="/register" class="nav-item" v-if="!isAuthenticated">Register</router-link>
            <button class="nav-item" @click="logout" v-if="isAuthenticated">Logout</button>
        </div>
    </nav>
</template>



<style type="sass" scoped>
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;

    color: #fff;

    .navbar-brand {
        color: #fff;
        text-decoration: none;
    }

    .nav-item {
        margin-left: 1rem;
        color: #fff;
        cursor: pointer;
        text-decoration: none;
    }

    .nav-item:hover {
        text-decoration: underline;
    }

    button {
        padding: 5px 15px;
        border-radius: 5px;
        background-color: #007bff;
        color: white;
        font-weight: bold;
        border: none;
        transition: 1s ease-in-out;
        cursor: pointer;
        margin: 10px 0;
    }
}
</style>