<template>
    <div>
        <b-jumbotron>
            <template slot="lead">
            {{currentQuestion.question}}            
            </template>

            <hr class="my-4">

            <b-list-group>
                <b-list-group-item 
                    v-for="(answer, index) in answers" 
                    :key="index"
                    @click="selectAnswer(index)"
                    :class="[selectedIndex === index ? 'selectedAnswer' : '']">
                   {{ answer }} 
                </b-list-group-item>                
            </b-list-group>
        
            <b-button variant="primary" href="#">Submit</b-button>
            <b-button @click="next" variant="success" href="#">Next</b-button>            
        </b-jumbotron>
    </div>
</template>

<script>
    export default {
        props: {
            currentQuestion: Object,
            next: Function
        },
        data() {
            return {
                selectedIndex: null
            }
        },
        computed: {
            answers(){ //de ce e definita var answers intr-o functie?
                let answers = [...this.currentQuestion.incorrect_answers]
                answers.push(this.currentQuestion.correct_answer)
                return answers
            }
        },
        methods: {
           selectAnswer(index) {
               this.selectedIndex = index               
           }
        },
        mounted() {
            console.log(this.currentQuestion)
        }
    }
</script>

<style scoped>
    .list-group {
        margin-bottom: 15px;
    }

    .list-group-item:hover {
        background: #EEE;
        cursor: pointer;
    }

    .btn {
        margin: 0 5px;
    }

    .selectedAnswer {
        background: lightblue;
    }

    .wrongAnswer {
        background: lightcoral;
    }

    .correctAnswer {
        background: lightgreen;
    }

</style>


