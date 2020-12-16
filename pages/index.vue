<template>
  <div>
    <div class="line1">
        <div class="board1">
            <div class="control"><button class="btn0" @click="decrement"><</button></div>
                <div v-for="projeto in projetos_filtrados" :key="projeto.id">
                    
                    <div class="card">
                        <p class="text0">{{projeto.nome}}</p>
                        <img :src="projeto.urlimage" width="200px" height="200px">
                        <p class="text1">{{projeto.tecnologia}}</p>
                        <p class="text2">{{projeto.description}}</p>
                        <div class="buttons">
                            <button class="btn1" v-show="count!==1"><a :href="projeto.urlproject" target="_blank" class="btn-link">Code</a></button>
                            <button class="btn2" v-show="count!==1">Demo</button>
                        </div>
                    </div>
                    

                </div>
            <div class="control"><button class="btn0" @click="increment">></button></div>
        </div>
        <div class="board2">
            <div v-for="tecnologia in tecnologias" :key="tecnologia.id">
                <p class="text3">{{tecnologia.nome}}</p>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            timeline: [
                {
                "urlimage":"",
                "description":"Bem-Vindo a meu portfólio! Arraste as imagens para o lado para conhecer minha história..."
                },
                {
                "year":1995,
                "urlimage":"",
                "description":"Primeiros passos..."
                },
                {
                "year":2000,
                "urlimage":"",
                "description":"Já era muito criativo, brincava muito de lego e desenhava..."
                },
                {
                "year":2005,
                "urlimage":"",
                "description":"Aluno que só tirava 10 em todas matérias na escola..."
                },
                {
                "year":2008,
                "urlimage":"",
                "description":"Já sabia editar vídeo e imagens (Photoshop, Illustrator e Sony vegas)..."
                },
                {
                "year":2010,
                "urlimage":"",
                "description":"Aprendizagem de HTML + CSS + Javascript..."
                },
                {
                "year":2012,
                "urlimage":"",
                "description":"Aprovado na faculdade de Engenharia de Produção com ênfase em Sistemas de Informação (UnB)..."
                },
                {
                "year":2013,
                "urlimage":"",
                "description":"Primeiro contato com programação - Linguagem C++ (if, else, for, while, string, array, matrix, functions)..."
                },
                {
                "year":2015,
                "urlimage":"",
                "description":" Criação de Jogos (Construct 2) + POO + Design Patterns + Bancos de Dados..."
                },
                {
                "year":2016,
                "urlimage":"",
                "description":" Trabalhos em grupo, métodos ágeis (SCRUM), trello, kanban, To-Do List e GitHub..."
                },
                {
                "year":2017,
                "urlimage":"",
                "description":"Processos + Testes + Docker + Nuvem (AWS) + Deploy..."
                },
                {
                "year":2018,
                "urlimage":"",
                "description":"Entrada no mercado de trabalho - Criação de Sites em Wordpress + Elementor...."
                },
                {
                "year":2019,
                "urlimage":"",
                "description":"Criação de Sites com Back-End (LARAVEL - PHP), NodeJS (Javascript) e Django (Python) + Criação e Consumo de APIs..."
                },
                {
                "year":2020,
                "urlimage":"",
                "description":"Aprendizado de Vue.js + Nuxt.JS + Figma + Adobe XD..."
                },
            ],

            projetos: [
                {
                "id": 1,
                "urlimage":"https://i.ibb.co/27zjPX9/avataaars.png",
                "nome":"Lucas Dev",
                "description":"Seja bem-vindo(a) ao meu portfólio! Clique nas setas ao lado para conhecer meus projetos..."
                },
                {
                "id": 2,
                "urlimage":"https://www.pngrepo.com/download/167046/tickets.png",
                "nome":"Aplicativo de tickets",
                "description":"Criar eventos e permitir a venda de ingressos (cinema, festas, shows, eventos esportivos, etc) via terminal de comando.",
                "tecnologia":"Linguagem C",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Aplicativos/tree/master/Aplicativo%20de%20Tickets"
                },
                {
                "id": 3,
                "urlimage":"https://images-na.ssl-images-amazon.com/images/I/41da3NERJ4L.png",
                "nome":"Aplicativo Fockus",
                "description":"Aplicativo para auxiliar no foco de terminar atividades diárias (Extensão para Chrome).",
                "tecnologia":"Javascript",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Aplicativos/tree/master/Aplicativo%20Fockus"
                },
                {
                "id": 4,
                "urlimage":"https://img.pngio.com/tickets-icon-png-222482-free-icons-library-ticket-icon-png-200_200.jpg",
                "nome":"Aplicativo de Rifas",
                "description":"Gerador de rifas dinâmicas na Web.",
                "tecnologia":"PHP",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Aplicativos/tree/master/Aplicativo%20de%20Rifas"
                },
                {
                "id": 5,
                "urlimage":"https://cdn.iconscout.com/icon/free/png-512/box-package-parcels-logistic-delivery-packed-shipping-11-20601.png",
                "nome":"Aplicativo Estokar",
                "description":"Permite controlar e gerenciar estoque (arquivos CSV) via terminal de comando",
                "tecnologia":"Python",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Aplicativos/tree/master/Aplicativo%20Estokar"
                },
                {
                "id": 6,
                "urlimage":"https://images.vexels.com/media/users/3/200098/isolated/preview/7ad7c76da9a0cd7d2b01b64b2590617b-shopping-cart-icon-shopping-cart-icon-by-vexels.png",
                "nome":"CRUD de Produtos",
                "description":"Cria, edita e deleta produtos com rotas dinâmicas.",
                "tecnologia":"Laravel + MySQL",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Frameworks/tree/master/CRUD%20Laravel"
                },
                {
                "id": 7,
                "urlimage":"https://img.icons8.com/cotton/2x/user-male-circle.png",
                "nome":"CRUD de Clientes",
                "description":"Cria, edita e deleta clientes na área administrativa.",
                "tecnologia":"Django + SQLite",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Frameworks/tree/master/CRUD%20Django"
                },
                {
                "id": 8,
                "urlimage":"https://static.thenounproject.com/png/196867-200.png",
                "nome":"API Trendapi",
                "description":"Consumo da API Google Trends via pytrends.",
                "tecnologia":"Python",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/APIs/tree/master/trendapi"
                },
                {
                "id": 9,
                "urlimage":"https://img.icons8.com/cotton/2x/worldwide-location--v2.png",
                "nome":"API Reservapi",
                "description":"Criação de API para Reservas em Hotéis usando Django Rest Framework.",
                "tecnologia":"Python + Django",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/APIs/tree/master/reservapi"
                },
                {
                "id": 10,
                "urlimage":"https://image.flaticon.com/icons/png/512/179/179546.png",
                "nome":"Portfólio",
                "description":"Criação de portfólio com slides.",
                "tecnologia":"VueJS + NuxtJS",
                "gif":"",
                "urlproject":"https://github.com/lucasbguima/Portfolio"
                },
            ],
            tecnologias: [
                {
                "id": 1,
                "nome":"C",
                },
                {
                "id": 2,
                "nome":"C++",
                },
                {
                "id": 3,
                "nome":"PHP",
                },
                {
                "id": 4,
                "nome":"POO",
                },
                {
                "id": 5,
                "nome":"Javascript",
                },
                {
                "id": 6,
                "nome":"Python",
                },
                {
                "id": 7,
                "nome":"HTML",
                },
                {
                "id": 8,
                "nome":"CSS",
                },
                {
                "id": 9,
                "nome":"Laravel",
                },
                {
                "id": 10,
                "nome":"Django",
                },
                {
                "id": 11,
                "nome":"NodeJS",
                },
                {
                "id": 12,
                "nome":"VueJS",
                },
                {
                "id": 13,
                "nome":"AWS",
                },
                {
                "id": 14,
                "nome":"Heroku",
                },
                {
                "id": 15,
                "nome":"Git",
                },
                {
                "id": 16,
                "nome":"GitHub",
                },
                {
                "id": 17,
                "nome":"Docker",
                },
                {
                "id": 18,
                "nome":"MySQL",
                },
                {
                "id": 19,
                "nome":"SQLite",
                },
                {
                "id": 20,
                "nome":"PostGreSQL",
                },
                {
                "id": 21,
                "nome":"MongoDB",
                },
                {
                "id": 22,
                "nome":"Vercel",
                },
                {
                "id": 23,
                "nome":"API",
                },
                {
                "id": 24,
                "nome":"Insomnia",
                },
                {
                "id": 25,
                "nome":"Postman",
                },
                {
                "id": 26,
                "nome":"Photoshop",
                },
                {
                "id": 27,
                "nome":"Illustrator",
                },
                {
                "id": 28,
                "nome":"Figma",
                },
                {
                "id": 29,
                "nome":"Whinsical",
                },
                {
                "id": 30,
                "nome":"NuxtJS",
                },
            ],
            count: 1,
        }
    },
    computed: {
        projetos_filtrados: function(){
            return this.projetos.filter(projeto => projeto.id === this.count);
            }
        },
    methods: {
        increment() {
            if (this.count < (this.projetos.length)){
                this.count += 1;
            }
            else {
                this.count = 1;
            }
                
            console.log(this.count)
        },
        decrement() {
            if (this.count > 1){
                this.count -= 1;
            }
            else {
                this.count = this.projetos.length;
            }
                
            console.log(this.count)
        }
    }
}

</script>

<style>
*{
    padding: 0;
    margin: 0;
    border: 0;
    outline: none;

}
.btn-link{
    text-decoration: none;
    color: white;
    padding: 10px;
}
.card{
    background-color: rgb(255, 255, 255);
    box-shadow: 0 1px 3px rgba(0,0,0,0.12);
    width: 200px;
    padding: 50px;
    border-radius: 20px;
}

.board1{
    background-color: rgb(151, 24, 255);
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    justify-items: center;
    align-items: center;
    height: 685px;
}
.board2{
    padding: 10px;
    background-color: rgb(0, 0, 0);
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    justify-items: stretch;
    align-items: center;
    gap: 10px;
}   
.line1{
    display: grid;
    grid-template-columns: repeat(1, 1fr);
}
.btn0{
    font-size: 30px;
    font-weight: bold;
    color:white;
    background-color: rgb(128, 128, 128, 0.5);
    border: none;
    border-radius: 5px;
    padding: 10px;
    box-shadow: 0 1px 3px rgba(0,0,0,0.12);
}
.btn1{
    font-size: 15px;
    font-weight: bold;
    color:white;
    background-color: rgb(17, 188, 255);
    border: none;
    padding: 10px;
    border-radius: 5px;
}
.btn2{
    font-size: 15px;
    font-weight: bold;
    color:white;
    background-color: rgb(165, 241, 142);
    border: none;
    padding: 10px;
    border-radius: 5px;
}
.text0{
    text-align: center;
    font-family: arial;
    font-weight: bold;
    padding-top: 10px;
    padding-bottom: 10px;
    color: rgb(100, 100, 100);
}

.text1{
    text-align: center;
    font-family: arial;
    padding-top: 10px;
    padding-bottom: 10px;
    color: rgb(27, 145, 255);
}

.text2{
    text-align: justify;
    font-family: arial;
    padding-top: 10px;
    padding-bottom: 10px;
}

.text3{
    color: white;
    text-align: center;
    font-family: arial;
}

.btn0,.btn1,.btn2:hover{
    cursor: pointer;
}
.text3:hover{
   cursor:default;
}

.buttons{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 10px;
}

@media screen and (min-width: 600px) {
    .line1{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
    }
}

</style>