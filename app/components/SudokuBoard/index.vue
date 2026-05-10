<template>
    <div
      v-for="(row, r) in board"
      :key="r"
      class="board-row"
    >
      <div
        v-for="(cell, c) in row"
        :key="c"
        class="cell"
      >
        {{ cell.value ?? '·' }}
      </div>
    </div>
</template>

<script setup lang="ts">
const emptyCell = () => ({ value: null as number | null, given: false, error: false })

const board = Array.from({ length: 9 }, () =>
  Array.from({ length: 9 }, emptyCell)
)
</script>

<style src="./styles.css" />