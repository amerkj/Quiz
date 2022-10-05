<template>
   <div class="result">
        <div class="title">you got a{{theResult.theRightAnswer}}  and lose {{theResult.theWrongAnswer}} </div>
        <div class="desc">
            Enter a short description here about the result.
        </div>
    </div>
</template>
<script>
    export default{
        props:{
            theResult:Object,
        }

    }
</script>