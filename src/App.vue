<template>
  <div>
    <header>
      <span id="ramoncito" @click="toggleAudio">CATALOGO POKÉMON DE TARJETAS</span>
      <div class="w3-container">
        <audio id="audio-player" ref="audioPlayer" :src="audioSrc"></audio>
      </div>
    </header>

    <div class="pokemon-container" id="pokemon-container">
      <!-- Aquí se mostrarán los Pokémon -->
    </div>

    <footer>
      <p>&copy; 2023 Pokémon Store</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      audioSrc: "https://www.cjoint.com/doc/23_09/MIwvlqlr3ad_Ven-a-Mí.mp3",
      isAudioPaused: true,
    };
  },
  methods: {
    toggleAudio() {
      const audioPlayer = this.$refs.audioPlayer;

      if (audioPlayer.paused) {
        audioPlayer.play();
      } else {
        audioPlayer.pause();
      }

      this.isAudioPaused = audioPlayer.paused;
    },
  },
};
</script>

<style scoped>
/* Estilo para el cursor de mano */
#ramoncito {
  cursor: pointer;
}
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-image: repeating-linear-gradient(284deg, transparent 0px, transparent 1px,rgb(251,251,251) 1px, rgb(251,251,251) 3px),repeating-linear-gradient(14deg, transparent 0px, transparent 1px,rgb(251,251,251) 1px, rgb(251,251,251) 3px),linear-gradient(90deg, rgb(222,222,222),rgb(222,222,222));

}

header {
    background-image: linear-gradient(90deg, #e60000, #ffcc00, #00529B); /* Combinación de colores Pokémon */

    text-align: center;
    padding: 20px 0;
}


#ramoncito {
    color:blanchedalmond;
    font-size: 30px;

}

footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
}

/* Estilos para el contenedor de productos Pokémon */
.pokemon-container {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); /* Diseño responsivo */
    gap: 20px;
    padding: 20px;
}

.pokemon-card {
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    padding: 10px;
    text-align: center;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.2);
    position: relative; /* Para controlar la posición del botón */
}

.pokemon-card img {
    max-width: 100%;
    height: auto;
    margin-bottom: 10px; /* Espacio entre la imagen y el botón */
}

.ver-button {
    background-color: #008CBA;
    color: white;
    font-size: 16px;
    font-weight: bold;
    border-radius: 5px;
    padding: 10px 20px;
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    transition: background-color 0.2s, transform 0.2s, box-shadow 0.2s;
}

.pokemon-card:hover {
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.4);
}

.ver-button:hover {
    background-color: #00529B;
    transform: translate(-50%, -2px);
    box-shadow: 0 0 10px #00529B;
}
</style>
