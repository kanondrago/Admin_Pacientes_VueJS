<script setup>

    import { computed, isVNode } from 'vue'

    const props = defineProps({
        alerta:{
            type: Object,
            required: true
        }
    })

    // En el template se utiliza corchetes para poner una condición
    const isError = computed(() => {
        return props.alerta.tipo === 'error'
    })

</script>

<template>
    <div
        :class="[isError ? 'bg-red-500': 'bg-green-500']"
        class="text-white text-center w-full rounded-md p-3 my-3 uppercase font-bold"
    >
        <h3>{{alerta.mensaje}}</h3>
    </div>
</template>