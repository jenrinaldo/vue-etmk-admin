<template>
    <div>
        <appmain></appmain> 
        <appheader></appheader>
        <appside></appside>
        <appoverlay></appoverlay>
    </div>
</template>

<script>

import Sidemenu from './components/Sidemenu.vue';
import Header from './components/Header.vue';
import Mainpage from './components/Main.vue';
import Overlay from './components/Overlay.vue';

export default {
    components: {
        appside : Sidemenu,
        appheader : Header,
        appmain : Mainpage,
        appoverlay : Overlay
    },
    data () {
        return {

        }
    }
}

</script>

<style>
    
    @import url('./assets/css/font-faces.css');
    @import url('./assets/css/flexboxgrid.min.css');
    @import url('./assets/css/font-awesome.css');

    * {
        margin: 0;
        padding: 0;
        border: 0;
        outline: 0;
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;
        text-decoration: none;
        -webkit-user-select: none;
        -moz-user-select: moz-none;
        -ms-user-select: none;
        user-select: none;
        list-style: none;
    }

    .raleway {
        font-family: 'Raleway', sans-serif;
    }

    .montserrat {
        font-family: 'Montserrat', sans-serif;
    }

    .left {
        float: left;
    }

    .right {
        float: right;
    }


</style>
