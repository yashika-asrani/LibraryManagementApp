<template>
    <div>
        <h1>{{id != 0 ? "Edit" : "Add"}} Books</h1>
        <!-- {{ book }} -->
        <v-form>
            <v-text-field label="Title" v-model="book.title"></v-text-field>
            <v-text-field label="Description" v-model="book.description"></v-text-field>
        </v-form>
    </div>
    </template>
<script>
import bookList from '@/data/books.json'
    export default {
        data() {
            return {
                id: 0,
                book: {},
            }
        },
        mounted () {
            this.id= this.$route.params.id;
            if(this.id !=0){
                this.book = bookList.find(rec=> rec._id == this.id)
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>