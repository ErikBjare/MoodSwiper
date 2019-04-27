<template>
  <div id="app">
    <GameCardsStack
      :cards="visibleCards"
      @cardAccepted="handleCardAccepted"
      @cardRejected="handleCardRejected"
      @cardSkipped="handleCardSkipped"
      @hideCard="removeCardFromDeck"
    />
  </div>
</template>

<script>
import GameCardsStack from "./components/GameCardsStack";

export default {
  name: "App",
  components: {
    GameCardsStack
  },

  data() {
    return {
      visibleCards: [
        { title: "Happy", emoji: "", emoji_class: "em em-grinning" },
        { title: "Sad", emoji: "", emoji_class: "em em-frowning" },
        { title: "Annoyed", emoji: "", emoji_class: "em em-angry" },
        { title: "Tired", emoji: "", emoji_class: "em em-sleepy" }
      ]
    };
  },

  methods: {
    handleCardAccepted(card) {
      console.log("handleCardAccepted", card);
    },
    handleCardRejected(card) {
      console.log("handleCardRejected", card);
    },
    handleCardSkipped(card) {
      console.log("handleCardSkipped", card);
    },
    removeCardFromDeck() {
      this.visibleCards.shift();
    }
  }
};
</script>

<style lang="scss">
@import "./styles/mixins.scss";

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  text-align: center;
}
</style>
