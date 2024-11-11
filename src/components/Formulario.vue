<template>
    <div class="container">
        <div>
            <label for="title">Título:</label>
            <input type="text" v-model="titulo"/>
        </div>
        <hr>
        <div>
            <label for="emoji">Emoji: </label>
            <select v-model="emoji">
                <option disabled value="">Selecciona un emoji</option>
                <option>👨‍💻</option>
            </select>
        </div>
        <hr>
        <div>
            <p>Apreciación: </p>
            <label><input type="radio" value="Regular" v-model="apreciacion" /> Regular</label>
            <label><input type="radio" value="Bien" v-model="apreciacion" /> Bien</label>
            <label><input type="radio" value="Muy Bien" v-model="apreciacion" /> Muy Bien</label>
            <label><input type="radio" value="Increible" v-model="apreciacion" /> Increible</label>
        </div>
        <hr>
        <div>
            <p>Competencias Aprendidas: </p> 
            <label><input type="checkbox" value="Morfología de un Componente" v-model="competencias" /> Morfología de un Componente</label>
            <label><input type="checkbox" value="Directivas" v-model="competencias" /> Directivas</label>
            <label><input type="checkbox" value="One-way y Two-way data bindin" v-model="competencias" /> One-way y Two-way data binding</label>
            <label><input type="checkbox" value="Estado" v-model="competencias" /> Estado</label>
            <label><input type="checkbox" value="El patrón de diseño MVVM" v-model="competencias" /> El patrón de diseño MVVM</label>  
        </div>
        <hr>
        <div>
            <label for="opinion">Opinión: </label>
            <textarea v-model="opinion"></textarea>
            
        </div>
    </div>

    <div>
        <h1 v-if="emoji">{{ emoji }}</h1>
        <h2 v-if="titulo">{{ titulo }}</h2>
        <p v-if="apreciacion">Y me parece {{ apreciacion }}</p>
        <p v-if="competencias.length">He Aprendido:</p>
        <p v-if="competencias.length">{{ competencias.join(', ') }}</p>
        <p v-if="opinion">Mi opinión hasta ahora del Framework es:</p>
        <p v-if="opinion">{{ opinion }}</p>
    </div>
</template>
  
<script>
    export default {
        name: 'Formulario',
        data() {
            return {
                titulo: '',
                emoji: '',
                apreciacion: '',
                competencias: [],
                opinion: ''
            }
        },
    }
  </script>
  
  <style scoped>
  .container{
    height: 400px;
    width: 600px;
    background-color: black;
    color: white;
    border-radius: 10px;
    padding: 40px 30px 30px;
  }
  </style>
  