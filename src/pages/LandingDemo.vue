<template>
    <div class="surface-0 overflow-hidden">
        <div class="py-4 px-4 mx-0 md:mx-6 lg:mx-8 lg:px-8 flex align-items-center justify-content-between relative lg:static">
            <router-link to="/" class="flex align-items-center">
                <img src="layout/images/LogAgro.jpg" alt="Sakai Logo" height="50" class="mr-0 lg:mr-2"><span class="text-900 font-medium text-2xl line-height-3 mr-8">MARKETAGRO</span>
            </router-link>
            <a class="cursor-pointer block lg:hidden text-700 p-ripple" v-ripple
                v-styleclass="{ selector: '@next', enterClass: 'hidden', leaveToClass: 'hidden', hideOnOutsideClick: true }">
                <i class="pi pi-bars text-4xl"></i>
            </a>
            <div class="surface-0 align-items-center flex-end-1 justify-content-end hidden lg:flex absolute lg:static w-full left-0 px-6 lg:px-30 z-2" style="top:92%">
                <div class="flex justify-content-between lg:block border-top-1 lg:border-top-none surface-border py-3 lg:py-0 mt-3 lg:mt-0">
                    <Button label="Inicio" class="p-button-text p-button-rounded border-none font-light line-height-2 text-blue-500"
                        v-on:click="loadHome"></Button>
                    <Button label="Registrarse" class="p-button-rounded border-none ml-5 font-light text-white line-height-2 bg-blue-500"
                    v-on:click="loadRegister"></Button>
                </div>
            </div>
        </div>

        <div class="grid py-4 px-4 lg:px-8 relative" id="hero">
            <div class="mx-4 md:mx-8 mt-0 md:mt-4">
                <h1 class="text-6xl font-bold text-gray-900 line-height-2"><span class="font-light block">Bienvenido a MARTEKAGRO</span>Tienda virtual de productos para el Agro</h1>
                <p class="font-normal text-2xl line-height-3 md:mt-3 text-gray-700">En esta tienda virtual encontra diferentes productos del Agro, como lo son fumigadoras, fertilizantes, herramientas, entre otros ... </p>
                <Button label="Ingresa" class="p-button-rounded text-xl border-none mt-5 bg-blue-500 font-normal text-white line-height-3 px-3"></Button>
                
            </div>
            <img src="layout/images/ladingFondo.jpg" class="bottom-0" height="350" alt="hero screen" style="right:10%; opacity: 0.8;">
        </div>
        
    </div>
</template>

<script>
export default {
    methods: {
        smoothScroll(id){
            document.querySelector(id).scrollIntoView({
                behavior: 'smooth'
            });
        },
        loadHome: function() {
            this.$router.push({ name: "login" });
        },
        loadRegister: function() {
            this.$router.push({ name: "Registro" });
        },
    },
    computed: {
        logoColor() {
            if (this.$appState.darkTheme) return 'white';
            return 'dark';
        }
    }


}
</script>

<style>
#hero{
    background: linear-gradient(0deg, rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0.2)), radial-gradient(77.36% 256.97% at 77.36% 57.52%, #EEEFAF 0%, #C3E3FA 100%);
    height:700px;
    overflow:hidden;
}

@media screen and (min-width: 768px) {
    #hero{
        -webkit-clip-path: ellipse(150% 87% at 93% 13%);
        clip-path: ellipse(150% 87% at 93% 13%);
        height: 530px;
    }
}

@media screen and (min-width: 1300px){
    #hero > img {
        position: absolute;
    }

    #hero > div > p { 
        max-width: 450px;
    }
}

@media screen and (max-width: 1300px){
    #hero {
        height: 600px;
    }

    #hero > img {
        position:static;
        transform: scale(1);
        margin-left: auto;
    }

    #hero > div {
        width: 100%;
    }

    #hero > div > p {
        width: 100%;
        max-width: 100%;
    }
}
</style>