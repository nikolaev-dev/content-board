<!-- src/lib/Card.svelte -->
<script lang="ts">
  export let title: string;
  export let description: string;
  export let onDelete: () => void;

  let isEditing = false;
  let newTitle = title;
  let newDescription = description;

  function toggleEditing() {
    isEditing = !isEditing;
  }

  function saveChanges() {
    title = newTitle;
    description = newDescription;
    isEditing = false;
  }
</script>

<div class="bg-white rounded-md p-3 mb-2 shadow-sm hover:shadow-md cursor-grab">
  {#if isEditing}
    <div>
      <input
        type="text"
        class="border p-2 mb-2 w-full"
        bind:value={newTitle}
        placeholder="Card Title"
      />
      <textarea
        class="border p-2 mb-2 w-full"
        bind:value={newDescription}
        placeholder="Card Description"
      ></textarea>
      <button class="bg-blue-500 text-white p-2 rounded" on:click={saveChanges}>Save</button>
    </div>
  {:else}
    <h3 class="font-bold text-gray-800 mb-2">{title}</h3>
    <p class="text-gray-600 text-sm">{description}</p>
    <div class="mt-2 flex justify-between items-center">
      <button class="text-blue-500" on:click={toggleEditing}>Edit</button>
      <button class="text-red-500" on:click={onDelete}>Delete</button>
    </div>
  {/if}
</div>
