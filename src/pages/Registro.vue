<template>
    <div class="surface-0 flex align-items-center justify-content-center min-h-screen min-w-screen overflow-hidden">
        <div class="grid justify-content-center p-2 lg:p-0" style="min-width:80%">
            <div class="col-12 mt-5 xl:mt-0 text-center">
                <img src="layout/images/agro.jpg" class="mb-5" style="width:120px; height:150px;">
            </div>
            <br>
            <br>
            <div class="col-12 xl:col-6" style="border-radius:56px; padding:0.3rem; background: linear-gradient(180deg, var(--primary-color), rgba(33, 150, 243, 0) 30%);">
                <div class="h-full w-full m-0 py-7 px-4" style="border-radius:53px; background: linear-gradient(180deg, var(--surface-50) 38.9%, var(--surface-0));">
                    <div class="text-center mb-5">
                        <div class="text-900 text-3xl font-medium mb-3">Bienvenido!</div>
                        <span class="text-600 font-medium">Ingrese para continuar</span>
                    </div>
                
                    <div class="w-full md:w-10 mx-auto">
                        <label for="email1" class="block text-900 text-xl font-medium mb-2">Username</label>
                        <InputText id="email1" v-model="Username" type="text" class="w-full mb-3" placeholder="Username" style="padding:1rem;" />
                
                        <label for="password1" class="block text-900 font-medium text-xl mb-2">Password</label>
                        <Password id="password1" v-model="password" placeholder="Password" :toggleMask="true" class="w-full mb-3" inputClass="w-full" inputStyle="padding:1rem"></Password>

                        <label for="email1" class="block text-900 text-xl font-medium mb-2">Email</label>
                        <InputText id="email1" v-model="email" type="text" class="w-full mb-3" placeholder="ejemplo@gmail.com" style="padding:1rem;" />

                        <label for="email1" class="block text-900 text-xl font-medium mb-2">Nombre</label>
                        <InputText id="email2" v-model="Nombre" type="text" class="w-full mb-3" placeholder="Pedro Peréz" style="padding:1rem;" />

                        <label for="email1" class="block text-900 text-xl font-medium mb-2">edad(Años)</label>
                        <InputNumber id="edad1" v-model="edad" type="text" showButtons  mode="decimal" class="w-full mb-3" placeholder="" style="padding:1rem;" />

                        <label for="email1" class="block text-900 text-xl font-medium mb-2">rol</label>
                        <Dropdown id="email1" v-model="dropdownValue" :options="dropdownValues" optionLabel="name" placeholder="Select"  style="padding:1rem;" />
                        
				


                        <Button label="Sign In" class="w-full p-3 text-xl"></button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            email: '',
            password: '',
            calendarValue: null,
            inputNumberValue: null,
            checked: false,
            dropdownValues: [
					{name: 'Admin', code: 'AD'},
					{name: 'Proveedor', code: 'PR'},
					{name: 'Usuario', code: 'US'}
				],
            dropdownValue: null,
        }
    },
    computed: {
        logoColor() {
            if (this.$appState.darkTheme) return 'white';
            return 'dark';
        }
    }
}
</script>

<style scoped>
.pi-eye {
    transform:scale(1.6);
    margin-right: 1rem;
}

.pi-eye-slash {
    transform:scale(1.6);
    margin-right: 1rem;
}

.Img img {
    height: 200px;
    display: block;
    border-radius: 200px;
    border: 1px solid white;
    margin: 100px auto 20px auto;
}
</style>