<template>
    <div>  
        <b-nav tabs>
            <b-nav-item><b>Inapoi</b></b-nav-item>
            <b-nav-item disabled>Counter: {{numOfCorrectAnsw}}/{{numOfTotal}}</b-nav-item>
        </b-nav>
    </div>
       
    
</template>

<script>
export default {    
    props: [
         "numOfCorrectAnsw",
         "numOfTotal"
    ]
    
}
</script>
