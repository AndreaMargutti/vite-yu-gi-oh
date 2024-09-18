<script setup>
// Importo i componenti
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
</script>

<template>
    <!--Inserisco i componenti principali-->
    <AppHeader />
    <AppMain />
</template>

<style  lang="scss">
// aggiungo il css di bootstraps
@use "../node_modules/bootstrap/scss/bootstrap.scss";
// aggiungo il mio css generico 
@use "./style/general.scss";
</style>
