<template>
  <div>
    <div v-if="campeonato && rodada"
      class="mt-10 pd-20 title-campeonato">
      <span class="bold"> {{campeonato}} </span> <span class="ronda">{{rodada}}</span>
    </div>
    <div class="row placar">
       <div
        v-if="time1"
        class="item">
         <span class="label-team bold">{{time1.sigla}}</span>
         <img :src="time1.logo" alt="">
       </div>
       <div v-if="time1 && time2"
        class="item result bold">
         <span> {{time1.gols}} </span>
         <span class="versus"> x </span>
         <span> {{time2.gols}}  </span>
       </div>
       <div v-if="time2"
        class="item">
         <img :src="time2.logo" alt="">
         <span class="label-team bold">{{time2.sigla}}</span>
       </div>
      </div>
  </div>
</template>
<script>
export default {
  name: 'Placar',
  props: {
    campeonato: String,
    rodada: String,
    time1: Object,
    time2: Object
  }
}
</script>
<style>
.item {
  display: inline;
}
.title-campeonato {
  color: #666;
}
.placar {
  max-height: 90px;
  font-size: 20px;
}
.placar img {
  vertical-align: bottom;
  width: 50px;
}
.placar > .result {
  margin: 20px;
  font-size: 30px;
}
.versus {
  font-size: 20px;
  font-weight: normal;
}
.label-team {
  align-items: center;
  line-height: 40px;
  margin: 10px;
}
</style>
