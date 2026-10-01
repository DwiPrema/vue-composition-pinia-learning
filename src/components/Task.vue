<script setup>
import { useTasksStore } from '@/stores/tasksStore.js';

const props = defineProps(['task'])

const store = useTasksStore()
</script>

<template>
    <div class="task">
        <h3>
            {{ task.name }}
        </h3>
        <p>
            {{ task.description }}
        </p>
        <div class="task-check">
            <input type="checkbox" @click="store.toggleCompleted(task.id)" :checked="task.completed" />
            <label>
                {{task.completed ? "Done" : "Todo"}}
            </label>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.task {
    display: flex;
    flex-direction: column;
    background-color: var(--white-color);
    color: var(--black-color);
    padding: 20px;
    border-radius: 12px;
    position: relative;


    h3 {
        font-size: 20px;
        font-weight: 700;
        line-height: 21px;
        letter-spacing: 0em;
        text-align: left;
    }

    p {
        margin-top: 24px;
        margin-bottom: 12px;
        font-size: 16px;
        font-weight: 400;
        line-height: 16px;
        letter-spacing: 0em;
        text-align: left;
    }


    .task-check {
        display: flex;
        align-items: center;
        justify-content: center;
        position: absolute;
        bottom: 10px;
        right: 10px;

        label {
            font-size: 13px;
            font-weight: 400;
            line-height: 16px;
            letter-spacing: 0em;
            text-align: left;
            margin-left: 5px;
            cursor: pointer;
        }

        input {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 18px;
            height: 18px;
            border-radius: 100%;
            border: 0.77px solid #AEAEB2;
            appearance: none;
            cursor: pointer;


            &:checked {
                background-color: #0A7AFF;
                border-color: #0A7AFF;

                &::before {
                    content: '';
                    display: block;
                    width: 4.5px;
                    height: 9px;
                    border: solid white;
                    border-width: 0 2px 2px 0;
                    transform: rotate(45deg);
                }
            }
        }
    }
}
</style>