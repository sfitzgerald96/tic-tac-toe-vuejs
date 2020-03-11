<template>
  <div>
    <div class="board-row">
      <Square :value="this.squares[0]" @updateSquare="$emit('updateSquare', 0)" />
      <Square :value="this.squares[1]" @updateSquare="$emit('updateSquare', 1)" />
      <Square :value="this.squares[2]" @updateSquare="$emit('updateSquare', 2)" />
    </div>
    <div class="board-row">
      <Square :value="this.squares[3]" @updateSquare="$emit('updateSquare', 3)" />
      <Square :value="this.squares[4]" @updateSquare="$emit('updateSquare', 4)" />
      <Square :value="this.squares[5]" @updateSquare="$emit('updateSquare', 5)" />
    </div>
    <div class="board-row">
      <Square :value="this.squares[6]" @updateSquare="$emit('updateSquare', 6)" />
      <Square :value="this.squares[7]" @updateSquare="$emit('updateSquare', 7)" />
      <Square :value="this.squares[8]" @updateSquare="$emit('updateSquare', 8)" />
    </div>
  </div>
</template>

<script>
import Square from './Square';

export default {
  name: "Board",
  components: {
    Square
  },
  props: ['squares'],
}
</script>

<style>
.board-row:after {
  clear: both;
  content: "";
  display: table;
}
.status {
  margin-bottom: 10px;
}
</style>