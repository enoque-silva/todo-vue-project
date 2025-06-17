<script setup>
    const props = defineProps(['cadastarTarefa', 'tarefaTemporaria', 'editaTarefaTemp', 'trocarFiltro'])
</script>
<template>
    <form @submit.prevent="props.cadastarTarefa">
        <div class="row">
            <div class="col">
                <input type="text" class="form-control" placeholder="Digite a tarefa" required
                    :value="props.tarefaTemporaria" 
                    @change="props.editaTarefaTemp"/>
            </div>
            <div class="col-md-2">
                <button type="submit" class="btn btn-primary">Cadastrar</button>
            </div>
            <div class="col-md-3">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="todas">Todas</option>
                    <option value="pendentes">Pendentes</option>
                    <option value="finalizadas">Finalizadas</option>
                </select>
            </div>
        </div>
    </form>
</template>