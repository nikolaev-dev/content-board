<!-- src/lib/Board.svelte -->
<script lang="ts">
  export let columns: Array<{ id: string, title: string, cards: Array<string> }> = [];
</script>

<div class="flex overflow-x-auto gap-4 p-4 h-[calc(100vh-80px)]">
  {#each columns as column}
    <div class="bg-gray-200 rounded-lg p-3 w-72 flex-shrink-0 h-full flex flex-col">
      <div class="font-bold mb-3 px-2 pb-2 border-b border-gray-300">
        {column.title}
      </div>
      <div class="overflow-y-auto flex-grow">
        {#each column.cards as card}
          <div class="bg-white rounded-md p-3 mb-2 shadow-sm hover:shadow-md cursor-grab">
            {card}
          </div>
        {/each}
      </div>
      <button class="mt-2 w-full py-2 bg-gray-300 text-gray-700 rounded hover:bg-gray-400 transition-colors">
        Add Card
      </button>
    </div>
  {/each}
</div>
