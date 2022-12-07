<template>
    <div id="main">
        <h1> {{title}} </h1>
        <h4>by- {{developerName}}</h4>
    </div>
</template>

    
    <script>
    
    export default{
        name: 'HeaderView',
        props:{
            title: String,
            developerName:String
        }
    }
    
    </script>
    
    <style scoped>
    
    #main{
        padding: 10px;
        background-color: #382a4b;
        text-align: center;
        grid-area: header;
        max-width: 100%;
        color: beige;
    
        /* align-content:space-around; */
    }
    #main h4{
        padding: 10px;
    }
    
    </style>