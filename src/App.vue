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
                    <li class="list">
                        <span class="item">テスト1</span>
                        <i class="fa fa-trash" aria-hidden="true"></i>
                    </li>
                </ul>
            </div>
            <div>
                <ul class="list-row">
                    <li class="list">
                        <span class="item">テスト2</span>
                        <i class="fa fa-trash" aria-hidden="true"></i>
                    </li>
                </ul>
            </div>
        </section>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
    setup() {
        const todo = ref('')

        return {
            todo,
        }
    },
})
</script>
