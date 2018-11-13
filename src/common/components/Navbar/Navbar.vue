<template>
   <nav>
      <div
        v-if="title"
        :style="style"
        class="nav-wrapper">
        <a href="#" class="brand-logo">{{title}}</a>
      </div>
      <i class="material-icons">add</i>
    </nav>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    title: String,
    color: String
  },
  computed: {
    style () {
      return 'background-color:' + this.color
    }
  }
}
</script>
