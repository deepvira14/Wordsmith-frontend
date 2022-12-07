<template>
    <div class="outterbox">


        

        <div v-for="word in words" :key="word.id" >
            <QuestionItem :word="word"/>
        </div>

    </div>
    


</template>'

<script>

    import QuestionItem from './QuestionItem.vue'


    export default{
        name: 'OutterBox',
        components: {
            QuestionItem
        },
        props:{
            
            words: Array
        }
    }

</script>

<style scoped>

.outterbox{

background-color: #382a4b;
padding: 1em;
color: gray;
}

</style>