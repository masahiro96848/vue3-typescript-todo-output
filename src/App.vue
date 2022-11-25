<template>
    <div class="container">
        <h1 class="title">Todo List</h1>
        <section class="container-area">
            <div>
                <input
                    class="input-area"
                    placeholder="Todoを追加"
                    type="text"
                />
            </div>
        </section>
        <!-- todoListのエリア -->
        <section class="container-area">
            <div>
                <input
                    class="input-area"
                    placeholder="キーワードを検索"
                    type="text"
                />
            </div>
        </section>
        <section class="container-area">
            <div>
                <ul class="list-row">
                    <li
                        v-for="(todo, index) in todoList.todos"
                        :key="index"
                        class="list"
                    >
                        <span class="item">{{ todo.title }}</span>
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
        // const todoList = ref(['test1', 'test2', 'test3'])
        const todoList = reactive({
            todo: '',
            todos: [
                {
                    title: 'テストサンプル1',
                },
                {
                    title: 'テストサンプル2',
                },
            ],
        })

        return {
            todoList,
        }
    },
})
</script>
