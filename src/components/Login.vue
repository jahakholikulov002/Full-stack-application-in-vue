<template >
    <div>
        <main class="form-signin w-25 m-auto mt-5">
            <form>
                <span>Jaha_dev</span>
                <h1 class="h3 mb-3 mt-3 fw-normal">Login</h1>


                <Input :label="'Email address'" :type="'email'" />
                <Input :label="'Password'" :type="'password'" />
                <Button type="submit">Login</Button>


            </form>
        </main>
    </div>
</template>
<script>
export default {

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