<script setup>
import { ref } from 'vue'

const tabela_camnac = ref([
  {
    id: 1,
    preco: 85.0,
    quantidade: 0,
    imagem: 'https://images.puma.com/image/upload/f_auto,q_auto,b_rgb:fafafa/global/773433/01/fnd/BRA/w/1000/h/1000/fmt/png',
    nome: 'Camisa Palmeiras Home 2023'
  },
  {
    id: 2,
    preco: 40.0,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-corinthians-ii-2324-sn-torcedor-nike-masculina/26/JD8-2730-026/JD8-2730-026_zoom1.jpg?ts=1681325953&ims=544x',
    nome: 'Camisa Corinthians Home 2023'
  },
  {
    id: 3,
    preco: 85.0,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-flamengo-i-2324-sn-torcedor-adidas-masculina/68/FB8-4631-068/FB8-4631-068_zoom1.jpg?ts=1674483941&?ims=544xhttps://static.netshoes.com.br/produtos/camisa-flamengo-i-2324-sn-torcedor-adidas-masculina/68/FB8-4631-068/FB8-4631-068_zoom1.jpg?ts=1674483941&?ims=1088x',
    nome: 'Camisa Flamengo Home 2023'
  }
])
function incrementar1(id) {
  console.log(tabela_camnac.value[id])
  tabela_camnac.value[id - 1].quantidade++
}
function decrementar1(id) {
  if (tabela_camnac.value[id - 1].quantidade > 0) {
    tabela_camnac.value[id - 1].quantidade--
  }
}

function adicionar1(id) {
  if (tabela_camnac.value[id - 1].quantidade > 0) {
    carrinho.value.itens.push({
      ...tabela_camnac.value[id - 1],
      preco: tabela_camnac.value[id - 1].quantidade * tabela_camnac.value[id - 1].preco
    })

    calcularTotal()
  }
}
const tabela_bolas = ref([
  {
    id: 1,
    preco: 70.0,
    quantidade: 0,
    imagem: 'https://m.media-amazon.com/images/I/61nmNfIKjeL._AC_SX679_.jpg',
    nome: 'Bola FIFA world cup 22'
  },
  {
    id: 2,
    preco: 65.0,
    quantidade: 0,
    imagem: 'https://images.tcdn.com.br/img/img_prod/1127564/bola_nike_academy_conmebol_libertadores_2023_1347_1_9c7f2370a2584b8d4b0675dc639e1e22.jpg',
    nome: 'Bola CONMEBOL Libertadores 23'
  },
  {
    id: 3,

    preco: 60.0,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/bola-de-futebol-copa-do-mundo-feminina-adidas-oceaunz-league/86/FB8-5254-086/FB8-5254-086_zoom1.jpg?ts=1674560404&ims=544x',
    nome: 'Bola FIFA Woman world cup 23'
  }
])
function incrementar2(id) {
  console.log(tabela_bolas.value[id])
  tabela_bolas.value[id - 1].quantidade++
}
function decrementar2(id) {
  if (tabela_bolas.value[id - 1].quantidade > 0) {
    tabela_bolas.value[id - 1].quantidade--
  }
}

function adicionar2(id) {
  if (tabela_bolas.value[id - 1].quantidade > 0) {
    carrinho.value.itens.push({
      ...tabela_bolas.value[id - 1],
      preco: tabela_bolas.value[id - 1].quantidade * tabela_bolas.value[id - 1].preco
    })

    calcularTotal()
  }}
const tabela_camint = ref([
  {
    id: 1,
    preco: 49.9,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-manchester-united-home-2223-sn-torcedor-adidas-masculina/16/3ZP-8883-016/3ZP-8883-016_zoom1.jpg?ts=1657716161',
    nome: 'Camisa Manchester United Home 2023'
  },
  {
    id: 2,

    preco: 39.9,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-nike-psg-i-20222023-torcedor-pro-masculina/08/2IC-9224-008/2IC-9224-008_zoom1.jpg?ts=1656710994&ims=544x',
    nome: 'Camisa PSG Home 23'
  },
  {
    id: 3,

    preco: 55.0,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-real-madrid-home-2223-sn-torcedor-adidas-masculina/14/3ZP-7305-014/3ZP-7305-014_zoom1.jpg?ts=1653414482&ims=544x',
    nome: 'Camisa Real Madrid Home 23'
  }
])
function incrementar3(id) {
  console.log(tabela_camint.value[id])
  tabela_camint.value[id - 1].quantidade++
}
function decrementar3(id) {
  if (tabela_camint.value[id - 1].quantidade > 0) {
    tabela_camint.value[id - 1].quantidade--
  }
}

function adicionar3(id) {
  if (tabela_camint.value[id - 1].quantidade > 0) {
    carrinho.value.itens.push({
      ...tabela_camint.value[id - 1],
      preco: tabela_camint.value[id - 1].quantidade * tabela_camint.value[id - 1].preco
    })

    calcularTotal()
  }}
const tabela_chut = ref([
  {
    id: 1,
    preco: 49.9,
    quantidade: 0,
    imagem: 'https://imgcentauro-a.akamaihd.net/500x500/M0XVW411/chuteira-society-adidas-x-speedportal-3-adulto-img.jpg',
    nome: 'Chuteira Society Adidas x speedportal 3'
  },
  {
    id: 2,
    preco: 40.0,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/chuteira-society-nike-beco-2-tf/58/HZM-3221-058/HZM-3221-058_zoom1.jpg?ts=1579716100',
    nome: 'Chuteira Society Nike Beco 2'
  },
  {
    id: 3,
    preco: 39.9,
    quantidade: 0,
    imagem: 'https://imgcentauro-a.akamaihd.net/500x500/M0QY4204/chuteira-de-campo-puma-future-z-4-4-adulto-img.jpg',
    nome: 'Chuteira de Campo Puma Future'
  }
  ])

  function incrementar4(id) {
    console.log(tabela_chut.value[id])
    tabela_chut.value[id - 1].quantidade++
  }
function decrementar4(id) {
    if (tabela_chut.value[id - 1].quantidade > 0) {
      tabela_chut.value[id - 1].quantidade--
    }
  }
function calcularTotal() {
    carrinho.value.total = 0.00;
    for (let item of carrinho.value.itens) {
      carrinho.value.total += item.quantidade * item.preco;
    }
  }

function adicionar4(id) {
    if (tabela_chut.value[id - 1].quantidade > 0) {
      carrinho.value.itens.push({
        ...tabela_chut.value[id - 1],
        preco: tabela_chut.value[id - 1].quantidade * tabela_chut.value[id - 1].preco
      })

      calcularTotal()
    }
  }
const carrinho = ref({
    itens: [],
    total: 0
  })

const mostrar = ref(false)

function remover(id) {
  let item = carrinho.value.itens.findIndex(item => item > id);
  carrinho.value.itens.splice(item, 1);
  calcularTotal()
}
</script>

<template>
  
  <h1>Passos Sports</h1>
    
    <div>
      <button class="btn-carrinho"  @click="mostrar = true"><a href="#carrinho">Carrinho 🛒</a></button>
    </div>
   
      <h2>Camisas de Clubes Nacionais</h2>
        <div class="marcas">
          <div v-for="(produto,index) in tabela_camnac" :key="index" class="produto">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
          <div class="informacoes" div>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar1(produto.id)">+</button>
            <button class="btn-decrementar" @click="decrementar1(produto.id)">-</button>
            <p>Quantidade de produto(s): {{ produto.quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar1(produto.id)">Adicionar ao Carrinho</button>
          </div>
        </div>
      </div>
   
        
    <div>
      <div id="tabela-bolas">
        <h2>Bolas de Futebol</h2>
        <div class="marcas">
          <div v-for="(produto, index) in tabela_bolas" :key="index" class="produto">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <div class="informacoes" div>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar2(produto.id)">+</button>
            <button class="btn-decrementar" @click="decrementar2(produto.id)">-</button>
            <p>Quantidade de produto(s): {{ produto.quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar2(produto.id)">Adicionar ao Carrinho</button>
          </div>
        </div>
      </div>
    </div>
      
      <div>
        <div id="tabela-camint">
        <h2>Camisas de Clubes Internacionais</h2>
        <div class="marcas">
          <div v-for="(produto, index) in tabela_camint" :key="index" class="produto">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <div class="informacoes">
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar3(produto.id)">+</button>
            <button class="btn-decrementar" @click="decrementar3(produto.id)">-</button>
            <p>Quantidade de produto(s): {{ produto.quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar3">Adicionar ao Carrinho</button>
          </div>
        </div>
      </div>
      </div>
      
      <div>
        <div id="tabela-chut">
        <h2>Chuteiras</h2>
        <div class="marcas">
          <div v-for="(produto, index) in tabela_chut" :key="index" class="produto">
            <img :src="produto.imagem" alt="" width="200" />
            <div class="informacoes">
            <h4>{{ produto.nome }}</h4>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar4(produto.id)">+</button>
            <button class="btn-decrementar" @click="decrementar4(produto.id)">-</button>
            <p>Quantidade de produto(s): {{ produto.quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar4(produto.id)">Adicionar ao Carrinho</button>
          </div>
        </div>
      </div>
    </div>
      </div>
      
  </div>
<div><div id="carrinho" v-if="mostrar">
     <h2>Carrinho de Compras </h2>
     <button @click="mostrar = false" class="btn-ocultar">Ocultar</button>
     <div id="item-carrinho" v-for="produto in carrinho.itens" :key="produto.id">
      <p>Item: {{ produto.nome }}</p>
      <p>Preco: {{ produto.preco.toFixed(2) }}</p>
      <p>Quantidade: {{ produto.quantidade }}</p>
      <div class="botao"><button @click="remover(produto.id)">Remover</button>
    </div></div>
    <p class="total">Total: R${{ carrinho.total.toFixed(2) }}</p>
  </div>
    </div></div>
  
</template>

<style scoped>
.marcas {
  display: flex;
  text-align: center;
  flex-direction: row;
}

h1 {
  text-align: center;
  font-family: 'calculadora';
  color: rgb(255, 255, 255);
  text-shadow: 5px 8px 8px rgb(63, 13, 156);
}

h2 {
  text-align: left;
  color: rgb(63, 13, 156);
  margin: 5px;
}

p {
  text-align: center;
  color: rgb(255, 255, 255);
}

img {
  border-radius: 8%;
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.473);
  margin-right: 60px;
  border-color: rgb(53, 16, 216);
  border-style: double;
  border-radius: 5px;
}

h4 {
  color: white;
  text-align: center;
  font-size: 20px;
}

h3 {
  text-shadow: 5px 7px 18px rgb(63, 13, 156);
  color: rgb(63, 13, 156);
}

button {
  color: white;
  background-color: rgb(145, 151, 228);
  border-color: white;
  border-style: double;
  border-radius: 5px;
}

button:hover {
  background-color: rgb(16, 10, 109);
  box-shadow: 2px 2px 5px rgba(40, 37, 223, 0.473);
}

hr {
  border-style: solid;
  color: white;
  margin: 10px;
}
@font-face {
    font-family: fonte;
    src: url('fontenumero.ttf');
}

body {
    font-family: fonte;
}

</style>
