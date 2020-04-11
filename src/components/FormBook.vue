<template>
    <div class="form">
        <form action="submit">
            <div class="form-group">

            </div>
            <div class="form row">
                <div class="col-md-1">
                    <span>Name:</span>
                </div>
                <div class="col-md-11">
                    <input v-model="name" type="text" class="form-control" placeholder="Name">
                    <label v-if="nameReq" id="nameRequired">The name field is required</label>
                </div>
            </div>
            <div class="form-row">
                <div class="form-group col-md-1">
                    <span>Edition:</span>
                </div>
                <div class="col-md-6">
                    <input v-model="edition" type="text" class="form-control" placeholder="Edition">
                    <label v-if="editionReq" id="nameRequired">The edition field is required</label>
                </div>

                <div class="col-md-1">
                    <span>Pages:</span>
                </div>
                <div class="col-md-4">
                    <input v-model="pages" type="text" class="form-control" placeholder="Pages">
                    <label v-if="pagesReq" id="nameRequired">The pages field is required</label>
                </div>
            </div>
            <div class="form-row">
                <div class="col-md-2">
                    <button v-on:click="register()" type="button" class="form-control btn btn-dark" id="btn">Register</button>
                </div>
            </div>
        </form>

    </div>
</template>

<script>
export default {
    name: 'FormBook',
    data() {
        return {
            name: '',
            edition: '',
            pages: '',
            nameReq: false,
            editionReq: false,
            pagesReq: false,
            sucess: false
        }
    },
    methods: {
        register() {
            if (this.name && this.edition && this.pages) {
                this.$emit("emit-book", {
                    name: this.name,
                    edition: this.edition,
                    pages: this.pages
                })
                this.name = ""
                this.edition = ""
                this.pages = ""
                this.nameReq = false
                this.editionReq = false
                this.pagesReq = false
                this.sucess = true
            } else {
                this.sucess = false
                this.nameReq = false
                this.editionReq = false
                this.pagesReq = false
                if (!this.name) {
                    this.nameReq = true
                }
                if (!this.edition) {
                    this.editionReq = true
                }
                if (!this.pages) {
                    this.pagesReq = true
                }
            }
        }
    }
}
</script>

<style>
div {
    margin-top: 0.3rem;
}

#btn {
    background-color: black;
    margin-top: 0.8rem;
}

#nameRequired {
    color: red
}
</style>

