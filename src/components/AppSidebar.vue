<template>
    <div class="container column">
        <form class="card card-w30">
        <div class="form-control">
            <label for="type">Тип блока</label>
            <select id="type">
            <option value="title">Заголовок</option>
            <option value="subtitle">Подзаголовок</option>
            <option value="avatar">Аватар</option>
            <option value="text">Текст</option>
            </select>
        </div>

        <div class="form-control">
            <label for="value">Значение</label>
            <textarea id="value" rows="3"></textarea>
        </div>

        <button class="btn danger">Добавить</button>
        </form>

        <app-card ></app-card>
    </div>
</template>
<script>
import AppCard from './AppCard.vue'

export default {
    components: {AppCard}
}
</script>