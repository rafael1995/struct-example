<template>
  <div class="row">
   <div class="col s12">
     <div
        v-if="escalacaoA && escalacaoB"
        class="ficha top-radius">
       <div class="nav-ficha top-radius">
          <span> FICHA DE JOGO </span>
        </div>
        <div class="team-one">
          <div v-for="jogador in escalacaoA" :key="jogador.nome">
              <div class="player">
                <div v-for="card in jogador.cards" :key="card.color">
                  <div class="item-cartao gol-left"/>
                </div>
                <div v-for="gol in jogador.gols" :key="gol.id">
                  <div class="item-gol gol-left"/>
                </div>
                <span class="name"> {{jogador.nome}}</span>
                <br>
                <span class="posicao">{{jogador.posicao}}</span>
              </div>
          </div>
        </div>
        <div class="team-two">
          <div v-for="jogador in escalacaoB" :key="jogador.nome">
              <div class="player">
                <div v-for="card in jogador.cards" :key="card.color">
                  <div class="item-cartao rigth"/>
                </div>
                <div v-for="gol in jogador.gols" :key="gol.id">
                  <div class="item-gol rigth"/>
                </div>
                <span class="name"> {{jogador.nome}}</span>
                <br>
                <span class="posicao">{{jogador.posicao}}</span>
              </div>
          </div>
        </div>
     </div>
   </div>
  </div>
</template>

<script>
export default {
  name: 'Escalacao',
  props: {
    escalacaoA: Array,
    escalacaoB: Array
  }
}
</script>
<style>
.ficha {
  border: solid 1px #dadada;
  min-height: 650px;
}
.nav-ficha {
  height: 32px;
  width: 100%;
  background-color: #3ea909;
  text-align: left;
  padding: 5px;
}
.nav-ficha span {
  font-weight: bold;
  color: #fff;
  font-size: 15px;
}
.team {
  width: 100%;
}
.team-one {
  width: 50%;
  float: left;
}
.team-two {
  width: 50%;
  float: left;
}
.player {
  margin: 5px;
  border-bottom: solid 1px #dadada;
}
.player .name {
  font-weight: bold;
  color: #333;
}
.player .posicao {
  color: #999;
}
.item-gol {
  width: 15px;
  height: 15px;
  background-image: url("../assets/ball.png")
}
.item-cartao {
  width: 15px;
  height: 15px;
  background-image: url("../assets/yellow-card.png")
}
.gol-left {
  float: left;
}
.rigth {
  float: right;
}
.team-one {
  text-align: right;
  padding-right: 5px;
}
.team-two {
  text-align: left;
  padding-left: 5px;
}
.top-radius {
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}
</style>
