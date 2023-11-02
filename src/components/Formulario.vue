<template>
    <div class="box">
        <div class="columns">
            <div class="column is-8" role="form" aria-label="Formulário para criação de uma nova tarefa">
                <input type="text" class="input" placeholder="Qual tarefa deseja iniciar?">
            </div>
            <div class="column">
                <div class="is-flex is-align-items-center is-justify-content-space-between">
                    <section>
                    <strong>{{ tempoDecorrido }}</strong>
                </section>
                <button class="button" @click="iniciarContagem">
                    <span class="icon">
                        <i class="fas fa-play"></i>
                    </span>
                    <span>play</span>
                </button>
                <button class="button" @click="finalizarContagem">
                    <span class="icon">
                        <i class="fas fa-stop"></i>
                    </span>
                    <span>stop</span>
                </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Formulario',
    data (){
        return {
            tempoSegundos: 0
        }
    },
    computed: {
        tempoDecorrido () : string {
            return new Date(this.tempoSegundos * 1000).toISOString().substr(11, 8)
        }
    },
    methods: {
        iniciarContagem(){
            console.log("A contagem iniciou.");
            setInterval(() => {
                console.log("incrementando contador");
                this.tempoSegundos += 1;
                console.log(this.tempoSegundos)
            }, 1000)

        },
        finalizarContagem(){
            console.log("A contagem finalizou")
        }
    }
})
</script>

<style>

</style>

