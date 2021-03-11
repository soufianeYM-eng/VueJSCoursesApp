<template lang="">
    <div class="row">
        <div class="col-md-6 mx-auto" v-show="showModal">
                <AddCourse @add='addCourse($event)'/>
        </div>
    </div>


    <div class="row">
        <div class="col-md-6 my-2">
            <nav style="--bs-breadcrumb-divider: '>';" aria-label="breadcrumb">
                <slot></slot>
            </nav>
            <h1>List of courses</h1>
        </div>
        <div class="col-md-6 text-right">
            <button class="btn btn-sm" :class="classObject" @Click="toggleDis">{{nameBtn}}</button>
        </div>
    </div>
    <div class="row">
        <div class="col-md-4" v-for="course in courses">
            <OneCourse :course="course" @delete="deleteOneCourse($event)" />
        </div>
    </div>
</template>
<script>

import OneCourse from './OnCourse';
import AddCourse from './AddCourse'; 

export default {
    components:{
        OneCourse,
        AddCourse,
    },
    data(){
        return{
            showModal:false,
            nameBtn : "New",
            courses : [
                {
                    id : 1,
                    title : "Learn VueJS",
                    image : "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/k7Fltx5ITbu9LI6VtgTS",
                },
                {
                    id: 2,
                    title: "Learn Laravel",
                    image: "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/WPcaz1wUQA6AltnnGc7l",
                },
                {
                    id: 3,
                    title: "Learn JavaScript",
                    image: "https://process.fs.teachablecdn.com/ADNupMnWyR7kCWRvm76Laz/resize=width:705/https://www.filepicker.io/api/file/H9QyEOsSLG05qNb2kC0V",
                }
            ]
        }
    },
    methods:{
        deleteOneCourse(id){
            this.courses = this.courses.filter(course => course.id !=id);
        },
        addCourse(course){
            this.courses.push(course);
            this.toggleDis();
        },
        toggleDis(){
            this.showModal = ! this.showModal;
            if(this.showModal==false){
                this.nameBtn="New";
            }
            else{
                this.nameBtn = "Close"
            }
        }
    },
    computed:{
        classObject(){

            return this.showModal ==true ? 'btn-dark' : 'btn-success';
        }
    }
}
</script>
<style lang="">
    
</style>