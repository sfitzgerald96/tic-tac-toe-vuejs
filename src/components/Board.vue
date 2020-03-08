<template>
  <div>
    <div class="status">{{ status }}</div>
    <div class="board-row">
      <Square :value="this.squares[0]" @updateSquare="handleClick(0)" />
      <Square :value="this.squares[1]" @updateSquare="handleClick(1)" />
      <Square :value="this.squares[2]" @updateSquare="handleClick(2)" />
    </div>
    <div class="board-row">
      <Square :value="this.squares[3]"  @updateSquare="handleClick(3)" />
      <Square :value="this.squares[4]"  @updateSquare="handleClick(4)" />
      <Square :value="this.squares[5]"  @updateSquare="handleClick(5)" />
    </div>
    <div class="board-row">
      <Square :value="this.squares[6]"  @updateSquare="handleClick(6)" />
      <Square :value="this.squares[7]"  @updateSquare="handleClick(7)" />
      <Square :value="this.squares[8]"  @updateSquare="handleClick(8)" />
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
  data: function() {
    return {
      status: "Next player: X",
      squares: Array(9).fill(null)
    };
  },
  methods: {
    handleClick(i) {
      this.squares[i] = "X";
    }
  }
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