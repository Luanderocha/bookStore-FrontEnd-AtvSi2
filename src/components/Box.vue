<template>
    <div>
        <FormBook v-on:emit-book="addBook"/>
        <div class="box" v-for="(b,index) in books" :key="index">
            <div class="form-row  back">
                <div class="col-mr-11">
                    <h4 class="book">Book N°{{index}}</h4>
                </div>
                <div class="col-mr-1">
                    <button v-on:click="removeBook(index)" type="button" class="btn btn-outline-secondary btn-sm">remove</button>
                </div>
            </div>
            <div class="form-row text-left">
                <div class="col-md-5">
                    <span>Name : {{b.name}}</span>
                </div>
                <div class="col-md-5 text-left">
                    <span>Edition : {{b.edition}}</span>
                </div>
                <div class="col-md-2 text-left">
                    <span>pages : {{b.pages}}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

import FormBook from './FormBook'

export default {
    name:'Box',
    components:{
        FormBook
    },
    data(){
        return{
            books:[]
        }
    },
    methods:{
        addBook(book){
           this.books.push(book);
        },
        removeBook(index){
            this.books.pop(index);
        }
    }
}
</script>

<style>
    .box{
        font-size: 0.9rem;
        border-bottom: 0.01rem solid gray;
        margin-top:0.8rem;
    }
    .book{
        margin-right: 1rem;
    }
    .back{
        background: rgb(230, 230, 230);
        border: 0.4rem solid transparent;
    }
</style>