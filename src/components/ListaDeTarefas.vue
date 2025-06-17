<script setup>
    const props = defineProps(['tarefas', 'tarefasPendentes']);
</script>

<template>
    <ul class="list-group mt-4">
        <li class="list-group-item" v-for="tarefa in props.tarefas">
            <input v-model="tarefa.finalizada" :id="tarefa.titulo" type="checkbox">
            <!-- <input @change="evento => tarefa.finalizada = evento.target.checked"  :checked="tarefa.finalizada" :id="tarefa.titulo" type="checkbox"> -->
            <label :class="{ done: tarefa.finalizada }" class="ms-3" :for="tarefa.titulo">
                {{ tarefa.titulo }}
            </label>
        </li>
    </ul>
    <ul v-if="props.tarefasPendentes == 0" class="list-group mt-4">
        <p class="text-center text-primary">Não existem tarefas pendentes</p>
    </ul>
</template>

<style scoped>
    .done {
        text-decoration: line-through;
    }
</style>