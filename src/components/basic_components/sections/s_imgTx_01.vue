<template>
<div :class="setOrder()">
    <img class="image-component" :src="data.imgLink">
    <span class="title">{{data.title}}</span>
    <p class="description-text">{{data.text}}</p>
</div>
</template>

<script>
export default {
    props: ['data','order'],
    name: 's_imgTx_01',
    components: {},
    methods: {
        setOrder: function() {
            if(this.order == 'img-text'){
                return 'image-text-container';
            }else{
                return 'text-image-container';
            }
        }
    }  
}
</script>

<style scoped>

.image-text-container{
    padding: 50px 0;
    border-width: 1px;
    border-style: solid;
    border-color: black;
    display: grid;
    grid-template-areas:
        '. image   .   .    .'
        '. image   . title  .'
        '. image   .  text  .'
        '. image   .   .    .';
    grid-template-columns: auto min-content auto min-content auto;
    grid-template-rows: auto min-content min-content auto;
}

.text-image-container{
    padding: 50px 0;
    border-width: 1px;
    border-style: solid;
    border-color: black;
    display: grid;
    grid-template-areas:
        '.   .     .   image    .'
        '. title   .   image    .'
        '. text    .   image    .'
        '.  .      .   image    .';
    grid-template-columns: auto min-content auto min-content auto;
    grid-template-rows: auto min-content min-content auto;
}

.description-text{
    color: gray;
    grid-area: text;
    text-align: center;
    font-size: 16px;
    min-width: 500px;
}

.image-component{
    border-radius: 50%;
    width: 350px;
    grid-area: image;
}

/* FONTS NEED TO BE GLOBAL */
.title{ 
    text-align: center;
    color: gray;
    font-size: 24px;
    grid-area: title;  
}
a{
    color: gray;
    text-decoration: none;
}
a:hover{
    color: rgb(21, 21, 70);
}

@media only screen and (max-width: 900px) {
    .image-text-container, .text-image-container{  
        grid-template-areas:
            'title title title title title'
            '  .   image image image   .'
            '  .   image image image   .'
            '  .   text  text  text    .';    
    }
    .image-component{
        margin: 0 auto;
        max-width: 350px;
        min-width: 200px;
        width: 80vw;
    }
    .description-text{
        text-align: center;
        width: 80vw;
        margin: 20px auto;
        min-width: 200px;
        max-width: 400px;
        
    }
    .title{
        margin-bottom: 20px;
    }
}

</style>