<template>
  <div v-if="partida">
   <Navbar
    :title="partida.campeonato"
    color="#3b9c00"
   />
   <Placar
    :campeonato="partida.campeonato"
    :rodada="partida.rodada"
    :time1="partida.time1"
    :time2="partida.time2"
    />
   <Escalacao
    :escalacaoA="partida.time1.escalacao"
    :escalacaoB="partida.time2.escalacao"
   />
  </div>
</template>

<script>
import Navbar from '../components/Navbar'
import Placar from '../components/Placar'
import Escalacao from '../components/Escalacao'
export default {
  name: 'Partida',
  props: {
    mstg: String
  },
  data () {
    return {
      partida: null
    }
  },
  methods: {
    getMatch () {
      let self = this
      this.$http.get('http://www.mocky.io/v2/5b79f2ec2e00006000c02940')
        .then(function (response) {
          self.partida = response.data.partida
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  },
  components: {
    Navbar,
    Placar,
    Escalacao
  },
  mounted () {
    this.getMatch()
  }
}
</script>

<style>
.mt-10 {
  margin-top: 10px;
}
.pd-20 {
  padding: 20px;
}
.bold {
  font-weight: bold;
}
</style>
