<template>
    <div class="game">
    <div class="game-board">
        <Board
            :squares="current.squares"
            @updateSquare="handleClick"
          />
    </div>
    <div class="game-info">
        <div>{{ status }}</div>
        <ol>
          <li v-for="(step, move) of history" :key="move">
            <button 
              @click="jumpTo(move)"
            >
              {{ move ? 'Go to move #' + move : 'Go to game start'}}
            </button>
          </li>
        </ol>
    </div>
    </div>
</template>

<script>
import Board from './Board.vue';
import {calculateWinner} from '../utilities/helperFunctions';

export default {
  name: "Game",
  components: {
    Board
  },
  data: function() {
    return {
      history: [{
        squares: Array(9).fill(null),
      }],
      stepNumber: 0,
      xIsNext: true,
    }
  },
  computed: {
    current: function() {
      return this.history[this.stepNumber];
    },
    status: function() {
      const winner = calculateWinner(this.current.squares);

      let status;
      if (winner) {
        status = 'Winner: ' + winner;
      } else {
        status = 'Next player: ' + (this.xIsNext ? 'X' : 'O');
      }

      return status;
    }
  },
  methods: {
    handleClick(i) {
      const history = this.history.slice(0, this.stepNumber + 1);
      const current = this.current;
      const squares = current.squares.slice();
      
      if (calculateWinner(squares) || squares[i]) {
        return;
      }
      
      squares[i] = this.xIsNext ? 'X' : 'O';

      this.history = history.concat([{
        squares: squares,
      }]),
      this.stepNumber = history.length
      this.xIsNext = !this.xIsNext
    },
    jumpTo(step) {
      this.stepNumber = step;
      this.xIsNext = (step % 2) === 0;
    }
  }
}
</script>

<style>
.game {
    display: flex;
    flex-direction: row;
}

.game-info {
    margin-left: 20px;
}
</style>

