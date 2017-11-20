<template>
  <div>
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>
  </div>
</template>

<script>
/* export default {
  name: 'app',
}; */
  import Todo from './components/Todo';
  import TodoList from './components/TodoList';
  import CreateTodo from './components/CreateTodo';

  export default {
    name: 'app',
    components: {
      TodoList,
      CreateTodo,
      Todo,
    },
  // data function avails data to the template
    data() {
      return {
        todos: [{
          title: 'Todo A',
          project: 'Project A',
          done: false,
        }, {
          title: 'Todo B',
          project: 'Project B',
          done: true,
        }, {
          title: 'Todo C',
          project: 'Project C',
          done: false,
        }, {
          title: 'Todo D',
          project: 'Project D',
          done: false,
        }],
      };
    },

    methods: {
      createTodo(newTodo) {
        this.todos.push(newTodo);
      },
    },
  };
</script>