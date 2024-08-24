<script>
export default {
    name: 'FormCard',
    data() {
        return {
            card: {
                title: '', //Visa Classic Crédito
                chipSrc: {
                    '1': 'src/assets/chip-silver.png',
                    '2': 'src/assets/chip-golden.png'
                }, // rutas de imagenes para el tipo de chip
                selectedChip: '', // índice del chip seleccionado 
                number: '', // 4000 5000 6000 7000
                expDate: '', // 01/30
                owner: '', //William Henry Gates III
                typeCard: '', // Visa, MasterCard, etc
            },
        }
    }
}
</script>
<template>
    <form>
        <div>
            <label>Título de la tarjeta: </label>
            <input v-model="card.title" type="text" />
        </div>

        <div>
            <label>Chip SRC: </label>
            <select class="form-select" v-model="card.selectedChip">
                <option selected disabled>Selecciona el tipo de Chip: </option>
                <option value="1">Chip Plateado</option>
                <option value="2">Chip Dorado</option>
            </select>
        </div>

        <div>
            <label>Número: </label>
            <input v-model="card.number" type="text" />
        </div>

        <div>
            <label>Fecha de expiración: </label>
            <input v-model="card.expDate" type="text" />
        </div>

        <div>
            <label>Propietario: </label>
            <input />
        </div>

        <div>
            <label>Tipo de tarjeta SRC: </label>
            <input />
        </div>
    </form>

    <div class="carnet">
        <h3>{{ card.title }}</h3>
        <img width="40" :src="card.chipSrc[card.selectedChip]" alt="" />
        <div>
            <h2>{{ card.number }}</h2>
            <span>Fecha Exp: <b>{{ card.expDate }}</b></span>
        </div>
        <footer>
            <span>William Henry Gates III</span>
            <img src="./../assets/visa.png" width="60" />
        </footer>
    </div>
</template>
<style scoped>
form {
    padding: 18px;
    border-radius: 20px;
    border: ridge 1px;
    box-shadow: 1px 1px 1px 1px gray;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    gap: 15px;
    justify-content: center;
}

form div {
    display: grid;
    grid-template-columns: 100px 200px;
    align-items: center;
    gap: 5px;
}

form div label {
    text-align: right;
}

.carnet {
    width: 400px;
    height: 230px;
    background: #1c1a1e;
    color: white;
    border-radius: 20px;
    padding: 20px;
    box-shadow: 0px 0px 10px 2px black;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

h3 {
    font-size: 20px;
}

h2 {
    font-size: 30px;
    letter-spacing: 10px;
    margin-bottom: 15px;
    text-shadow: 0px 0px 1px gold;
    font-family: Times;
}

b {
    font-size: 16px;
}

footer {
    display: flex;
    justify-content: space-between;
    align-items: flex-end;
    font-weight: bold;
    font-size: 18px;
    text-transform: uppercase;
    font-style: italic;
}
</style>