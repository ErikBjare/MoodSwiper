<template>
  <div class="cards">
    <GameCard
      v-for="(card, index) in cards"
      :key="card.title"
      :card="card"
      :is-current="index === 0"
      @cardAccepted="$emit('cardAccepted', card);"
      @cardRejected="$emit('cardRejected', card);"
      @cardSkipped="$emit('cardSkipped', card);"
      @hideCard="$emit('hideCard');"
    />
  </div>
</template>

<script>
import GameCard from "@/components/GameCard";

export default {
  components: {
    GameCard
  },

  props: {
    cards: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss" scoped>
.cards {
  position: relative;
  display: flex;
  margin: 50px;
  width: 300px;
}
</style>
