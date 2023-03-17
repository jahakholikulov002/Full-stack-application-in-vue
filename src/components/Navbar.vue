<template >
    <div class="d-flex flex-column flex-md-row align-items-center py-3 mb-4 border-bottom">
        <a href="/" class="d-flex align-items-center text-dark text-decoration-none" @click="$router.push('/')">
            
           <span>Jaha_dev</span> 
        </a>

        <nav class="d-inline-flex mt-2 mt-md-0 ms-md-auto">
            <a class="me-3 py-2 text-dark text-decoration-none"  @click="$router.push('/login')">Login</a>
            <a class="me-3 py-2 text-dark text-decoration-none" @click="$router.push('/register')">Register</a>
      
        </nav>
    </div>
</template>
<script>
export default {

}
</script>
<style scoped >
span{
    cursor: pointer;
    font-size: 2rem;
    font-weight: 700;
    border: 4px solid black;
    padding: 0 1rem;
    font-style:oblique;
}
a{
    cursor: pointer;
    font-size: 1.3rem;
    font-weight: 450;
}
</style>