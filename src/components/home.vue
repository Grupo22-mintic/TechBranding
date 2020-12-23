<template>
    <div>
        <div class="container-fluid">
            <div class="row mt-md-5 mt-sm-5 mt-xs-5">
                <div v-for="(art,indice) of datos" :key="art.id" class="col-lg-3 col-xs-12 border">
                    <div v-if="indice<=3">
                        <div  class="d-flex justify-content-center align-items-center">

                            <div class="p-3">
                                <!-- <svg width="12em" height="12em" viewBox="0 0 16 16" class="bi bi-alarm-fill" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" d="M6 .5a.5.5 0 0 1 .5-.5h3a.5.5 0 0 1 0 1H9v1.07a7.001 7.001 0 0 1 3.274 12.474l.601.602a.5.5 0 0 1-.707.708l-.746-.746A6.97 6.97 0 0 1 8 16a6.97 6.97 0 0 1-3.422-.892l-.746.746a.5.5 0 0 1-.707-.708l.602-.602A7.001 7.001 0 0 1 7 2.07V1h-.5A.5.5 0 0 1 6 .5zM.86 5.387A2.5 2.5 0 1 1 4.387 1.86 8.035 8.035 0 0 0 .86 5.387zM11.613 1.86a2.5 2.5 0 1 1 3.527 3.527 8.035 8.035 0 0 0-3.527-3.527zM8.5 5.5a.5.5 0 0 0-1 0v3.362l-1.429 2.38a.5.5 0 1 0 .858.515l1.5-2.5A.5.5 0 0 0 8.5 9V5.5z"
                                    />
                                </svg> -->
                                <img src = "https://i.pinimg.com/474x/fd/92/9c/fd929cf759206d1ee6d2266fb3878016.jpg" width="100%" height="100%"><img/>
                                <div class="p-2">
                                    <h4 style="text-align: center">
                                        {{art.nombre}}
                                    </h4>
                                    <p style="text-align: center">
                                        {{art.descripcion}}
                                    </p>
                                    <button type="button" class="btn btn-outline-info btn-block">Informacion</button>
                                </div>
                                
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="container-fluid">
            <h2 class="titulo-miembros">{{ tituloEquipo }}</h2>
            <div class="card-deck">
                <div class="card"  v-for = "(item , index) of team" :key = "index">
                    <TeamCard v-bind:member = "item" /> 
                </div>
            </div>
            <br>
        </div>
    </div>
</template>


<script>
import axios from 'axios';
import TeamCard from './TeamCard'

export default {
    components: {TeamCard},
    data() {
        return {
            datos: null,
            tituloEquipo : 'EQUIPO DE TRABAJO',
            team: [{
                codigo: 1,
                nombre: 'FRANCISCO ASTUDILLO',
                descripcion: 'Francisco Astudillo, quien actualmente es residente de la ciudad de Cali. Graduado como Ingeniero Ambiental en la Universidad del Valle y por ultimo, pero no menos importante, su deporte favorito es BMX.',
                rol: 'Desarrollador backend',
                image: "./img/Francisco-Astudillo.jpg"
                },
            
                {
                codigo: 2,
                nombre: 'JULIAN JIMENEZ ORTIZ',
                descripcion: 'Julian Jimenez Ortiz, Ingeniero Geologo graduado en la Universidad Nacional de Colombia, actualmente se encuentra viviendo en la ciudad de Florencia, donde aprovecha el tiempo para practicar piano, manejar bicicleta y juagr volley.',
                rol: 'Desarrollador backend',
                image: './img/Julian-Jimenez-Ortiz.png'
                },

                {
                codigo: 3,
                nombre: 'KEWIN PASSOS G.',
                descripcion: 'Kewin Passos G. graduado de la Universidad Nacional de Colombia como Ingeniero Forestal y que actualmente es residente de la ciudad de Medellin, hoy en dia dedica parte de su tiempo a desarrollar actividades para cumplir la mision MINTIC 2022.',
                rol: 'Desarrollador backend',
                image: './img/Kewin-Passos-G.jpg'
                },

                {
                codigo: 4,
                nombre: 'MATEO CARVAJAL',
                descripcion: 'Mateo Carvajal, un amante de los motores y la tecnologia, logro graduarse como Ingeniero Mecatronico de la Universidad de Caldas, ademas de ser tecnologo en mecatronica automotriz con tan solo 25 años.',
                rol: 'Desarrollador backend',
                image: './img/Mateo-Carvajal.png'
                },

                {
                codigo: 5,
                nombre: 'CRISTIAN CABARCAS',
                descripcion: 'Cristian Cabarcas, quien actualmente es residente de la ciudad de Cartagena, se encuentra siguiendo los pasos de sus compañeros para lograr una profesion al igual que ellos, dedicando su tiempo al estudio.',
                rol: 'Desarrollador backend',
                image: './img/Cristian-Cabarcas.jpg'
                }]
        };
    },
    mounted() {
     axios.get('articulo/list')
    .then(response => (this.datos = response.data));

    },
    
}
</script>

<style>
  .card-deck{

    margin-left: 0px;
    margin-right: 0px; 
    max-width: 1600px;
    min-width: 1300px;
  }  

  .card{

    height: 100%;
    border-radius: 10px;
  }

  .titulo-miembros{
    margin-top: 5px;
    margin-left: 15px;
    margin-right: 15px;
    text-align: center;
    background: rgb(108 117 125)!important;
    border-radius: 20px;
    max-width: 1600px;
  }

</style>