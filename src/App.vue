<template>
    <div class="container">
        <h1 class="title">Todo List</h1>
        <section class="container-area">
            <div>
                <input
                    v-model="state.todo"
                    class="input-area"
                    placeholder="Todoを追加"
                    type="text"
                />
                <button @click="addTodo">追加</button>
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
import { defineComponent, ref, reactive } from 'vue'

export default defineComponent({
    setup() {
        const state = reactive({
            todo: '',
            todos: [],
        })

        const addTodo = () => {
            state.todos.push(state.todo)
            state.todo = ''
        }

        return {
            state,
            addTodo,
        }
    },
})
</script>
