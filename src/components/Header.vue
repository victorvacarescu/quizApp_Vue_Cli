<template>
    <div>  
        <b-nav tabs>
            <b-nav-item><b>Inapoi</b></b-nav-item>
            <b-nav-item disabled>Counter: 1/10</b-nav-item>
        </b-nav>
    </div>
       
    
</template>

<script>
export default {
    name: 'Header',
    props: {
        msg: String,
    }
}
</script>
