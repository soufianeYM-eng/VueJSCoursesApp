<template lang="">
    <div class="form-group">
        <label for="title">Title </label>
        <input ref="title" id="title" type="text" class="form-control mb-2">
    </div>

    <div class="form-group">
        <label for="image">Image URL</label>
        <input ref="image" id="image" type="text" class="form-control mb-2">
    </div>
    <button @Click="NewCourse" class="btn btn-block btn-warning"> Add Course </button>
</template>
<script>
export default {
    methods:{
        NewCourse(){
            let title = this.$refs.title.value;
            let image = this.$refs.image.value;

            if(title == "" || image==""){
                return;
            }
            const course = {
                title,
                image
            }

            this.$emit('add',course);
            this.$refs.title.value="";
            this.$refs.image.value="";
        }
    }
}
</script>
<style lang="">
    
</style>