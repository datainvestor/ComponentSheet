<template>
  <div class="home">
    <!-- Basic static prop passing using hardcoded data -->
    <static-prop msg="Hello this is static"></static-prop>
    <!-- dynamic binding using one variable with if else, reusing component -->
    <!-- booleans and numbers need to be binded, is-list is used to change to different style component -->
    <dynamic-prop :is-list="false" :dynamicmsg="test || 'no message at all'"></dynamic-prop>
    <!-- if message is not found -->
    <dynamic-prop :is-list="false" :dynamicmsg="test2 || 'no message at all'"></dynamic-prop>
    <!-- passing single value from a list in comopnent -->
    <dynamic-prop :is-list="true" :id="todos[1].id" :dynamicmsg="todos[1].title"> </dynamic-prop>
    <dynamic-prop :is-list="true" :id="todos.find(element => element.id == 2).id" :dynamicmsg="todos.find(element => element.id == 2).title"> </dynamic-prop>
    <dynamic-prop :is-list="true" :id="2" :dynamicmsg="todosjs[2].title"></dynamic-prop>
    <!-- passing object value -->
    <object-prop :author="{
      name: 'Steven',
      company: 'Veridian Dynamics'
    }"></object-prop>
    <!-- Dynamic binding variables using list -->
    <dynamic-prop
      :is-list="true"
      v-for="item in todos"
      :key="item.id"
      :id="item.id"
      :dynamicmsg="item.title"
    ></dynamic-prop>
    <!-- pass variable to a class in a prop -->
    <class-prop classtag="colored"></class-prop>
    <!-- pass prop based on route -->
    <!-- This is actually mostly done in index.js file (router) and then accept the prop in the component -->
  </div>
</template>

<script>
// @ is an alias to /src
import StaticProp from "../components/StaticProp.vue";
import DynamicProp from "../components/DynamicProp.vue"
import ObjectProp from "../components/ObjectProp.vue"
import ClassProp from "../components/ClassProp.vue"

export default {
  name: "Home",
  components: {
    StaticProp,
    DynamicProp,
    ObjectProp,
    ClassProp
  },
  //data must be a function, even in parent comopnent (since Home.vue is a comopnent too)
  data: () => ({
    todos: [
      { id: 1, title: "Learn Python" },
      { id: 2, title: "Learn JS" },
      { id: 3, title: "Create WebApp" }
    ],
    test: "Hello this is dynamic",
    //Here we set up the array in a different way so that it can be accessed more easily
    todosjs: { 
       1: { title: "Learn Python" },
       2: { title: "Learn JS" },
       3: {title: "Create WebApp"} 
     }
  }),
};
</script>
