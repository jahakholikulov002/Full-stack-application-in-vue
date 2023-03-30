<template >
    <div>
        <main class="form-signin w-25 m-auto mt-5">
            <form>
                <span>Jaha_dev</span>
                <h1 class="h3 mb-3 mt-3 fw-normal">Register</h1>
                <ValidationError v-if="validationErrors" :validationErrors="validationErrors"/>
                <Input :label="'Name'" :type="'text'" v-model="username" />
                <Input :label="'Email address'" :type="'email'" v-model="email" />
                <Input :label="'Password'" :type="'password'" v-model="password" />




                <Button type="submit" :disabled="isLoading" @click="submitHandler">Register</Button>
            </form>
        </main>
    </div>
</template>
<script>
import ValidationError from "@/components/ValidationError.vue"
export default {
    data() {
        return {
            email: '',
            username: '',
            password: ''
        }
    },
    components: {
        ValidationError,
    },
    computed: {
        isLoading() {
            return this.$store.state.auth.isLoading
        },
        validationErrors(){
            return this.$store.state.auth.errors
        }
    },
    methods: {
        submitHandler(e) {
            e.preventDefault();
            const data = {
                username: this.username,
                email: this.email,
                password: this.password,
            }
            this.$store.dispatch('register', data)
                .then(user => {
                    console.log("user", user)
                    this.$router.push('home')
                })
                .catch((err) => console.log("Error", err))
        }
    }
}
</script>
<style  scoped>
span {
    cursor: pointer;
    font-size: 2rem;
    font-weight: 700;
    border: 4px solid black;
    padding: 0 1rem;
    font-style: oblique;
    cursor: pointer;
}
</style>