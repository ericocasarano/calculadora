<script setup>
const props = defineProps(['selecionaOperacao', 'capturaNum1', 'capturaNum2', 'renderizaResultado'])
</script>

<template>
    <h1>Calculadora Aritimética</h1>
    <select @change="props.selecionaOperacao" name="select-option" id="select-option">
        <option value="Somar">Somar</option>
        <option value="Subtrair">Subtrair</option>
        <option value="Dividir">Dividir</option>
        <option value="Multiplicar">Multiplicar</option>
    </select>
    <div class="numbers">
        <input @keyup="props.capturaNum1" type="number">
        <input @keyup="props.capturaNum2" type="number">
    </div>

    <p>
        Resultado: {{ props.renderizaResultado }}
    </p>
</template>


<style scoped>
.container {
    max-width: 600px;
    width: 100%;
    margin: 0 auto;
}

.container h1 {
    text-align: center;
}

.container .numbers {
    display: flex;
    margin: 20px 0;
    gap: 10px;
}

.container .numbers input {
    padding: 20px;
    text-align: center;
    width: 100%;
    font-size: 50px;
}
</style>
