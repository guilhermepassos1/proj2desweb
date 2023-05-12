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
const produtos_bt = ref([
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
const produtos_bocaRosa = ref([
  {
    id: 1,
    preco: 49.9,
    quantidade: 0,
    imagem: '',
    nome: 'Pó Boca Rosa Beauty'
  },
  {
    id: 2,
    preco: 40.0,
    quantidade: 0,
    imagem: '',
    nome: 'Corretivo Líquido - Boca Rosa'
  },
  {
    id: 3,
    preco: 39.9,
    quantidade: 0,
    imagem: 'https://static.netshoes.com.br/produtos/camisa-flamengo-i-2324-sn-torcedor-adidas-masculina/68/FB8-4631-068/FB8-4631-068_zoom1.jpg?ts=1674483941&?ims=544xhttps://static.netshoes.com.br/produtos/camisa-flamengo-i-2324-sn-torcedor-adidas-masculina/68/FB8-4631-068/FB8-4631-068_zoom1.jpg?ts=1674483941&?ims=1088x',
    nome: 'Boca Rosa by Payot Tint'
  }
])
const quantidade = 0
const carrinho = ref({
  itens: [],
  total: 0,

})
function incrementar(index) {
  tabela_camnac.value[index].quantidade++
}
function decrementar(index) {
  if (tabela_camnac.value[index].quantidade > 0) {
    tabela_camnac.value[index].quantidade--
  }
}

function adicionar(index) {
  if (tabela_camnac.value[index].quantidade > 0) {

    carrinho.value.itens.push(
      { ...tabela_camnac.value[index], preco: tabela_camnac.value[index].quantidade * tabela_camnac.value[index].preco }
    );

    carrinho.value.total = carrinho.value.total + tabela_camnac.value[index].preco * tabela_camnac.value[index].quantidade

  }

}
</script>

<template>
  <div id="loja-completa">
    <h1>Passos Sports</h1>
    <div>
      <button>Carrinho</button>
    </div>
    <div id="produtos">
      <div id="produtos-Mari">
        <h2>Camisas Nacionais</h2>
        <div class="marcas">
          <div v-for="(produto, index) in tabela_camnac" :key="index">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar(index)">+</button>
            <img src="lixeira.png" alt="" width="25" class="btn-deletar" @click="resetar" />
            <button class="btn-decrmentar" @click="decrementar(index)">-</button>
            <p>Quantidade de produto(s): {{ quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar">Adicionar ao Carrinho</button>
          </div>
        </div>

      </div>
      <hr>
      <div id="produtos-BT">
        <h2>Bruna Tavares</h2>
        <div class="marcas">
          <div v-for="(produto, index) in produtos_bt" :key="index">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar">+</button>
            <img src="lixeira.png" alt="" width="25" class="btn-deletar" @click="resetar" />
            <button class="btn-decrmentar" @click="decrementar">-</button>
            <p>Quantidade de produto(s): {{ contador }}</p>
            <button class="btn-adicionar" @click="adicionar">Adicionar ao Carrinho</button>

          </div>
        </div>

      </div>
      <hr>
      <div id="produtos-Fran">
        <h2>Fran</h2>
        <div class="marcas">
          <div v-for="(produto, index) in tabela_camint" :key="index">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar">+</button>
            <img src="lixeira.png" alt="" width="25" class="btn-deletar" @click="resetar" />
            <button class="btn-decrmentar" @click="decrementar">-</button>
            <p>Quantidade de produto(s): {{ contador }}</p>
            <button class="btn-adicionar" @click="adicionar">Adicionar ao Carrinho</button>

          </div>
        </div>

      </div>
      <hr>
      <div id="produtos-bocaRosa">
        <h2>Boca Rosa Beauty</h2>
        <div class="marcas">
          <div v-for="(produto, index) in produtos_bocaRosa" :key="index">
            <img :src="produto.imagem" alt="" width="200" />
            <h4>{{ produto.nome }}</h4>
            <h3>R${{ produto.preco.toFixed(2) }}</h3>
            <button class="btn-adicionar" @click="incrementar">+</button>
            <img src="lixeira.png" alt="" width="25" class="btn-deletar" @click="resetar" />
            <button class="btn-decrmentar" @click="decrementar">-</button>
            <p>Quantidade de produto(s): {{ produto.quantidade }}</p>
            <button class="btn-adicionar" @click="adicionar">Adicionar ao Carrinho</button>
          </div>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
.marcas {
  display: flex;
  justify-content: space-between;
  text-align: center;
  flex-direction: row;
}

h1 {
  text-align: center;
  font-family: 'URW Chancery L, cursive';
  color: rgb(255, 255, 255);
  text-shadow: 5px 5px 5px rgb(73, 6, 37);
}

h2 {
  text-align: left;
  color: rgb(255, 0, 98);
  margin: 5px;
}

p {
  text-align: center;
  color: rgb(97, 4, 40);
}

img {
  border-radius: 50%;
  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.473);
}

img>.btn-deletar {
  box-shadow: none;
}

h4 {
  color: white;
  text-align: center;
  font-size: 20px;
}

h3 {
  text-shadow: 5px 5px 10px rgb(255, 0, 106);
  color: rgb(255, 0, 98);
}

button {
  color: white;
  background-color: rgb(228, 145, 172);
  border-color: white;
  border-style: double;
  border-radius: 5px;
}

button:hover {
  background-color: rgb(201, 83, 122);
  box-shadow: 2px 2px 5px rgba(223, 37, 130, 0.473);
}

hr {
  border-style: solid;
  color: white;
  margin: 10px;
}
</style>
