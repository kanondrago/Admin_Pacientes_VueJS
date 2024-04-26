<script setup>
    import { ref, reactive } from 'vue';

    // reactive SIEMPRE es un objeto
    const paciente = reactive({
        nombre: '',
        propietario: '',
        email: '',
        alta: '',
        sintomas: ''
    });

    const validar = () => {

        if(Object.values(paciente).includes('')){
            alert('Valores Vacios')
            return
        }

        console.log('Agregando...')
    }

</script>


<template>
    <div class="md:w-1/2">
        <h2 class="font-black text-3xl text-center">Seguimiento de pacientes</h2>
        <p class="text-lg mt-5 text-center mb-10">
            Añade pacientes y 
            <span class="text-indigo-600 font-bold">adminístralos</span>
        </p>

        <form 
            class="bg-white shadow-md rounded-lg py-10 px-5 mb-10"
            action=""
            v-on:submit.prevent="validar"
        >
            
            <div class="mb-5">
                <label 
                    class="block text-gray-700 uppercase font-bold"
                    for="mascota"
                >
                    Nombre mascota
                </label>

                <input 
                    id="mascota"
                    type="text"
                    placeholder="Nombre de la mascota"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
                    v-model="paciente.nombre"
                >
            </div>

            <div class="mb-5">
                <label 
                    class="block text-gray-700 uppercase font-bold"
                    for="propietario"
                >
                    Nombre del propietario
                </label>

                <input 
                    id="propietario"
                    type="text"
                    placeholder="Nombre del propietario"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
                    v-model="paciente.propietario"
                >
            </div>

            <div class="mb-5">
                <label 
                    class="block text-gray-700 uppercase font-bold"
                    for="email"
                >
                    Email
                </label>

                <input 
                    id="email"
                    type="email"
                    placeholder="Email del propietario"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
                    v-model="paciente.email"
                >
            </div>

            <div class="mb-5">
                <label 
                    class="block text-gray-700 uppercase font-bold"
                    for="alta"
                >
                    Alta
                </label>

                <input 
                    id="alta"
                    type="date"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md"
                    v-model="paciente.alta"
                >
            </div>

            <div class="mb-5">
                <label 
                    class="block text-gray-700 uppercase font-bold"
                    for="sintomas"
                >
                    Sintomas
                </label>

                <textarea 
                    id="sintomas"
                    placeholder="Describe los sintomas"
                    class="border-2 w-full p-2 mt-2 placeholder-gray-400 rounded-md h-40"
                    v-model="paciente.sintomas"
                />
            </div>

            <input
                type="submit"
                class="bg-indigo-600 w-full p-3 text-white uppercase font-bold hover:bg-indigo-700 cursor-pointer transition-colors rounded-md"
                value="Registrar paciente"
            />

        </form>
    </div>
</template>