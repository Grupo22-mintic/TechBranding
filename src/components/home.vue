<template>
    <div>
        <div class="container-fluid">
            <div class="row mt-md-5 mt-sm-5 mt-xs-5">
                <div v-for="(art,indice) of datos" :key="art.id" class="col-lg-3 col-xs-12 border">
                    
                    <div v-if="indice<=10">
                        <div  class="d-flex justify-content-center align-items-center">
                            <div class="p-3">
                                <img src = "https://pbs.twimg.com/profile_images/1276188468666916869/BJpV2HMr.jpg" width="100%" height="100%"><img/>
                                <div class="p-2">
                                    <h4 style="text-align: center">
                                        {{ art.nombre}} 
                                    </h4>
                                    <p>{{ art.descripcion }}</p>
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
            dialog: false,
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