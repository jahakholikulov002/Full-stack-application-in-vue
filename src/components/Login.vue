<template >
    <div>
        <main class="form-signin w-25 m-auto mt-5">
            <form>
                <span>Jaha_dev</span>
                <h1 class="h3 mb-3 mt-3 fw-normal">Login</h1>
                <ValidationError v-if="validationErrors" :validationErrors="validationErrors" />
                <Input :label="'Email address'" :type="'email'" v-model="email" />
                <Input :label="'Password'" :type="'password'" v-model="password" />
                <Button type="submit" :disabled="isLoading" @click="submitHandler">Login</Button>
            </form>
        </main>
    </div>
</template>
<script>
import { mapState } from 'vuex'
import ValidationError from "@/components/ValidationError.vue"
export default {
    data() {
        return {
            email: '',
            password: ''
        }
    },
    components: {
        ValidationError,
    },
    computed: {
        ...mapState({
            isLoading: state => state.auth.isLoading,
            validationErrors: state => state.auth.errors,
        })
    },
    methods: {
        submitHandler(e) {
            e.preventDefault();
            const data = {
                username: this.username,
                email: this.email,
                password: this.password,
            }
            this.$store.dispatch('login', data)
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