<template>
    <div id="burger-table">
        <Message :msg="msg" v-show="msg"/>
        <div id="burger-table-heading">
            <div class="order-id">#:</div>
            <div>Cliente</div>
            <div>Pao</div>
            <div>Carne</div>
            <div>Opcionais</div>
            <div>Acao</div>
        </div>
     
        <div id="burger-table-rows">
            <div v-for="pedido in burgers" :key="pedido.id" class="burger-table-row">
                <div class="order-id">{{pedido.id}}</div>
                <div>{{pedido.nome}}</div>
                <div>{{pedido.pao}}</div>
                <div>{{pedido.carne}}</div>
                <div>
                    <ul>
                        <li v-for="opcional,index in pedido.opcionais" :key="index">{{opcional}}</li>
                    </ul>
                </div>
                <div class="acao">
                    <select name="status" class="status" @change="updateBurger($event,pedido.id)">
                        <option value="">Selecione</option>
                        <option v-for="s in status" :key="s.id" :value="s.tipo" :selected="pedido.status == s.tipo" >{{s.tipo}}</option>
                    </select>
                    <button class="delete-btn" @click="deleteBurguer(pedido.id)">Cancelar</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Message from './Message.vue'

export default{
    name:"Dashboard",
    data(){
        return{
            burgers: null,
            burger_id: null,
            status: [],
            msg: null
        }
    },
    components:{ Message },
    methods:{
        async getPedidos(){
            const req = await fetch("http://localhost:3000/burgers")
            const data = await req.json()

            this.burgers = data

            // resgatar status
            this.getStatus()
        },
        async getStatus(){
            const req = await fetch("http://localhost:3000/status")
            const data = await req.json()

            this.status = data
        },
        async deleteBurguer(id){
            const req = await fetch(`http://localhost:3000/burgers/${id}`,{
                method: "DELETE"
            })


            //msg
            this.msg = `Hamburger de ${id} foi cancelado`
            setTimeout(()=>this.msg = null,3000)
            this.getPedidos()
            
        },
        async updateBurger(e,id){
            const option = e.target.value

            const dataJson = JSON.stringify({status:option})
            const req = await fetch(`http://localhost:3000/burgers/${id}`,{
                method: "PATCH",
                headers: {"Content-Type": "application/json"},
                body: dataJson
            })

            const res = await req.json()

            console.log(res)
        } 
    },
    mounted(){
        this.getPedidos()
    }
}
</script>

<style scoped>
    #burger-table{
        max-width: 1200px;
        margin: 0 auto;
    }

    #burger-table-heading,
    #burger-table-rows,
    .burger-table-row{
        display: flex;
        flex-wrap: wrap;
    }
    #burger-table-heading{
        font-weight: bold;
        padding: 10px;
        border-bottom: 3px solid #333;
    }

    #burger-table-heading div,
    .burger-table-row div{
        width: 17%;
    }

    .burger-table-row{
        width: 100%;
        padding: 12px;
        border-bottom: 1px solid #ccc;
    }

    #burger-table-heading .order-id,
    .burger-table-row .order-id{
        width: 5%;
    }

    select{
        padding: 12px 6px;
        margin-right: 12px;
    }

    .delete-btn{
        background-color: #222;
        color: #fcba03;
        font-weight: bold;
        border: 2px solid #222;
        padding: 10px;
        font-size: 16px;
        margin: 0 auto;
        cursor: pointer;
        transition: 0.5s;
    }

    .delete-btn:hover{
        background-color: transparent;
        color: #222
    }

    .burger-table-row .acao{
    }
</style>