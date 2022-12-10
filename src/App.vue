<template>
    <div class="container">
        <h1 class="title">Todo List</h1>
        <section class="container-area">
            <form action="" @submit.prevent="handleAddTodo">
                <input
                    v-model="state.todo"
                    class="input-area"
                    placeholder="Todoを追加"
                    type="text"
                />
            </form>
        </section>
        <!-- todoListのエリア -->
        <TodoList :todo="state.todo" :todos="state.todos" />
    </div>
</template>

<script setup lang="ts">
import { reactive } from 'vue'
import TodoList from './components/TodoList.vue'
import { Todo } from './types/Todo'

const state = reactive<Todo>({
    todo: '',
    todos: [],
})

const handleAddTodo = () => {
    if (state.todo === '') {
        return
    }
    state.todos.push(state.todo)
    state.todo = ''
}
</script>
