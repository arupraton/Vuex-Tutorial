<template>
    <div>
        Filter Todos:
        <select @change="filterT($event)">
            <option value="200">200</option>
            <option value="100">100</option>
            <option value="50">50</option>
            <option value="20">20</option>
            <option value="10">10</option>
            <option value="5">5</option>
        </select>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
export default {
    name:'FilterTodos',
    methods: {
        ...mapActions(['filterTodos']),
        filterT(event){
            this.$bar.start()
            this.filterTodos(event)
                .then(() =>{
                    this.$bar.finish()
                })
        }
    }
}
</script>

<style>

</style>
