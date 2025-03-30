<!-- src/lib/Board.svelte -->
<script lang="ts">
  import Card from './Card.svelte';

  export let columns: Array<{ id: string, title: string, cards: Array<{ id: string, title: string, description: string }> }> = [];

  function deleteCard(columnId: string, cardId: string) {
    const column = columns.find(c => c.id === columnId);
    if (column) {
      column.cards = column.cards.filter(card => card.id !== cardId);
    }
  }
</script>

<div class="flex overflow-x-auto gap-4 p-4 h-[calc(100vh-80px)]">
  {#each columns as column}
    <div class="bg-gray-200 rounded-lg p-3 w-72 flex-shrink-0 h-full flex flex-col">
      <div class="font-bold mb-3 px-2 pb-2 border-b border-gray-300">
        {column.title}
      </div>
      <div class="overflow-y-auto flex-grow">
        {#each column.cards as card (card.id)}
          <Card
            title={card.title}
            description={card.description}
            onDelete={() => deleteCard(column.id, card.id)}
          />
        {/each}
      </div>
      <button class="mt-2 w-full py-2 bg-gray-300 text-gray-700 rounded hover:bg-gray-400 transition-colors">
        Add Card
      </button>
    </div>
  {/each}
</div>
