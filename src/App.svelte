<script lang="ts">
  import Board from './lib/Board.svelte';

  let columns = [
    {
      id: 'column-1',
      title: 'To Do',
      cards: [
        { id: 'card-1', title: 'Task 1', description: 'This is the description for Task 1' },
        { id: 'card-2', title: 'Task 2', description: 'This is the description for Task 2' },
        { id: 'card-3', title: 'Task 3', description: 'This is the description for Task 3' },
      ]
    },
    {
      id: 'column-2',
      title: 'In Progress',
      cards: [
        { id: 'card-4', title: 'Task 4', description: 'This is the description for Task 4' },
        { id: 'card-5', title: 'Task 5', description: 'This is the description for Task 5' },
      ]
    },
    {
      id: 'column-3',
      title: 'Completed',
      cards: [
        { id: 'card-6', title: 'Task 6', description: 'This is the description for Task 6' },
      ]
    },
  ];
</script>

<Board {columns} />
