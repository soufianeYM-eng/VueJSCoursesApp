<template lang="">
    <div class="card my-3">
                <img class="card-img-top" :src="course.image" alt="course.title">
                <div class="card-body">
                    <h4 class="card-title">{{ course.title }}</h4>
                    <p class="card-text">Lorem ipsum dolor, sit amet consectetur adipisicing elit. Veniam nobis ad iste, inventore veritatis saepe ipsa maiores reiciendis error, repellendus necessitatibus commodi quisquam tempora alias quae.</p>
                    <button class="btn btn-sm btn-danger"  @Click="deleteOne(course.id)">Delete</button>
                </div>
            </div>
</template>
<script>
export default {    
    props:['course'],
    methods:{
        deleteOne(id){
            this.$emit('delete',id);
        }
    }
}
</script>
<style lang="">
    
</style>