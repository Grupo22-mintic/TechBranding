<template>
    <div class="container-component">    
        <img class="card-img-top member" v-bind:src = member.image alt="Miembro del equipo">
        <div class="card-body-team">
            <p class="cabecera" style="text-align: center">Team Member<span> {{ member.codigo }}:  {{ member.rol }}</span></p>
            <h5 class="card-title nombre-miembro">{{ member.nombre }}</h5>
            <p class="card-text">{{ member.descripcion }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "TeamCard",
        props: ['member']
    }
</script>

<style>
    .container-component{

        min-height: 590px;
        padding: 10px;
        background: rgb(108 117 125)!important;
        border-radius: 10px;
    }


    .card-body-team{

        padding-left: 0px;
        padding-right: 0px;
        padding-top: 5px;
        padding-bottom: 5px;
    }

    .card-body-team > p{

        text-align: justify;
        margin-bottom: 0px;
    }

    .code{

        font-size: 25px;
    }

    .member{

        height: 230px;
    }
    .nombre-miembro{

        font-size: 19px;
        text-align: center;
    }
</style>