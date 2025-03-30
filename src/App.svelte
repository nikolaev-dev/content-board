<script lang="ts">
  import Board from './lib/Board.svelte';

  let columns = [
    { id: 'column-1', title: 'To Do', cards: ['Task 1', 'Task 2', 'Task 3'] },
    { id: 'column-2', title: 'In Progress', cards: ['Task 4', 'Task 5'] },
    { id: 'column-3', title: 'Completed', cards: ['Task 6'] },
  ];
</script>

<Board {columns} />
