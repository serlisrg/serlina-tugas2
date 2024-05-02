<template>
  <div class="container mt-5">
    <!-- Elemen judul dengan class dan style bindings -->
    <h1 :class="{ 'text-warning': isHighlighted }" :style="{ color: titleColor }">Selamat Datang di Halaman Web Saya</h1>
    
    <!-- Elemen paragraf -->
    <p>{{ message }}</p>
    
    <!-- Elemen input teks -->
    <input type="text" class="form-control" v-model="inputText" @input="handleInput" placeholder="Ketik sesuatu...">
    
    <!-- Elemen tombol dengan event listener -->
    <button class="btn btn-primary" @click="toggleHighlight">Toggle Highlight</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      
      isHighlighted: false,
      titleColor: 'blue',
      
      inputText: '',
     
      message: 'Ini adalah sebuah paragraf.'
    };
  },
  methods: {
    
    handleInput(event) {
      
      this.inputText = event.target.value;
     
      this.message = `Anda mengetik: ${this.inputText}`;
    },
    
    toggleHighlight() {
     
      this.isHighlighted = !this.isHighlighted;
    }
  }
};
</script>

<style scoped>

.text-warning {
  background-color: yellow;
}
</style>
