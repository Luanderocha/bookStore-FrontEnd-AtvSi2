<template>
    <div class="form">
        <form action="submit">
            <div class="form-row">
                <div class="col-md-1">    
                <span>Name:</span>
                </div>
                <div class="col-md-11">
                    <input v-model="name" type="text" class="form-control" placeholder="Name">
                </div>
            </div>

    <div class="form-row">
        <div class="col-md-1">
            <span>Edition:</span>
        </div>
        <div class="col-md-6">
            <input v-model="edition" type="text" class="form-control" placeholder="Edition">
        </div>
        <div class="col-md-1">
            <span>Pages:</span>
        </div>
        <div class="col-md-4">
            <input v-model="pages" type="text" class="form-control" placeholder="Pages">
        </div>
    </div>
        </form>
        <button v-on:click="register()" type="button" class="form-control btn btn-dark" id="btn">Register</button>
    </div>
</template>

<script>

export default {
    name:'FormBook',
    data(){
        return{
            name:'',
            edition:'',
            pages:null
        }
    },
    methods:{
        register(){
            if(!this.name || !this.edition || !this.pages){
                return 
            }

            this.$emit("emit-book",{
                name:this.name,
                edition:this.edition,
                pages:this.pages
            })

            this.name = ""
            this.edition = ""
            this.pages = ""
        }
    }
}
</script>

<style>
    div{
        margin-top: 0.3rem;
    }
    #btn{
        margin-top:0.8rem;
    }
</style>

