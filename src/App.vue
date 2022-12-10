<template>
    <div class="container">
        <h1 class="title">Todo List</h1>
        <section class="container-area">
            <div>
                <form action="" @submit.prevent="handleAddTodo">
                    <input
                        v-model="state.todo"
                        class="input-area"
                        placeholder="Todoを追加"
                        type="text"
                    />
                </form>
            </div>
        </section>
        <!-- todoListのエリア -->
        <section class="container-area">
            <div>
                <ul class="list-row">
                    <li
                        v-for="(todo, index) in state.todos"
                        :key="index"
                        class="list"
                    >
                        <span class="item">{{ todo }}</span>
                        <i class="fa fa-trash" aria-hidden="true"></i>
                    </li>
                </ul>
            </div>
        </section>
    </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'

export default defineComponent({
    setup() {
        type Todo = {
            todo: string
            todos: Array<string>
        }

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

        return {
            state,
            handleAddTodo,
        }
    },
})
</script>
