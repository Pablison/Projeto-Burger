
<template>
    <div>
        <p>Componente</p>
        <div>
            <form id="burger-form">
                <div class="input-container">
                    <label for="nome">Nome do Cliente:</label>
                    <input type="text" id="nome" name="nome" v-model="nome" placeholder="Digite seu nome">
                </div>
                <div class="input-container">
                    <label for="pao">Escolha o pão:</label>
                    <select name="pao" id="pao" v-model="pao">
                        <option value="">Selecione seu pão</option>
                        <option value="">Integral</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="carne">Escolha a carne do seu Burger:</label>
                    <select name="carne" id="carne" v-model="carne">
                        <option value="">Selecione o tipo de carne</option>
                        <option value="alcatra">Alcatra</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="opcionais">Selecione os opcionais:</label>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                        <span>Salame</span>
                    </div>
                </div>
                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Gerar meu Burger">
                </div>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    name: "BurgerForm"    
}
</script>

<style scoped>
    #burger-form{
        max-width: 400px;
        margin: 0 auto;
    }

    .input-container{
        display: flex;
        flex-direction: column;
    }
    
</style>