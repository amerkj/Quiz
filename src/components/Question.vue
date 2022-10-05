<template>
   <div class="questions-ctr">
        <div class="progress">
            <div class="bar" :style="{width: `${(questionAnswerd/questions.length)*100}%`}"></div>
            <div class="status">{{questionAnswerd}} of {{questions.length}}</div>
        </div>
        <div class="single-question" v-for=" (question,qi) in questions " v-show ="questionAnswerd == qi ">
            <div class="question" >{{question.q}}</div>
            <div class="answers" v-for="answer in question.answers">
                <div class="answer" @click.prevent="process(answer.is_correct,qi)" >{{answer.text}}</div>
                
            </div>
        </div>
    </div>
</template>
<script>
    export default{
        props:{
            questions: Array,
            questionAnswerd:Number
        },
        emits:["resultOfAnswer"],
        methods:{
            process(theResultOfAnswer,qi){
                let theResultOfAnswerAndIndex ={theResultOfAnswer:theResultOfAnswer,qi:qi}
                
                this.$emit("resultOfAnswer",theResultOfAnswerAndIndex)
            }
        }
    }
</script>