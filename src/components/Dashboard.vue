<template>
        <table id="burger-table">
            <thead>
                <tr id="burger-table-heading">
                    <th class="order-id">#id</th>
                    <th>Cliente</th>
                    <th>Pão</th>
                    <th>Carne</th>
                    <th>Opcionais</th>
                    <th>Ações</th>
                </tr>
            </thead>
            <tbody id="burger-table-rows">
                <tr class="burger-table-row" v-for="burger in burgers" :key="burger.id">
                    <td class="order-number">{{ burger.id}}</td>
                    <td>{{ burger.nome}}</td>
                    <td>{{ burger.pao}}</td>
                    <td>{{ burger.carne}}</td>
                    <td>
                        <ul>
                            <li v-for="(opcional, index) in burger.opcionais" :key="index">
                                {{opcional}}
                            </li>
                        </ul>
                    </td>
                    <td>
                        <select name="status" class="status">
                            <option>Selecione</option>
                        </select>
                        <button class="delete-btn">Cancelar</button>
                    </td>
                </tr>
            </tbody>
        </table>
</template>

<script>
export default {
    name: "Dashboard",
    data(){
        return {
            burgers: null,
            burger_id: null,
            status: [],
        }
    },
    methods: {
        async getPedidos(){
            const req = await fetch("http://localhost:3000/burgers");

            const data = await req.json();

            this.burgers = data

            console.log(this.burgers);
        }
    },
    mounted(){
        this.getPedidos();
    }
}
</script>

<style scoped>

#burger-table {
    width: 100%;
    margin: 0 auto;
}
 
#burger-table-heading,
#burger-table-rows,
.burger-table-row {
    display: flex;
    flex-wrap: wrap;
}

#burger-table-heading {
    font-weight: bold;
    padding: 12px;
    border-bottom: 3px solid #333;
}

#burger-table-heading th,
.burger-table-row td{
    width: 19%;
    text-align: left;
}

.burger-table-row {
    width: 100%;
    padding: 12px;
    border-bottom: 1px solid #CCC;
} 

#burger-table-heading .order-id,
.burger-table-row .order-number{
    width: 5%;
}

select {
    padding: 8px 6px;
    margin-right: 12px;
}

.delete-btn {
    background-color: #222;
    color: #fcba03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
}

.delete-btn:hover {
    background-color: transparent;
    color: #222;
}

</style>
