<script lang="ts">
    export let names: string[] = [];
</script>

{#each names as name}
    <h3>Hello {name}</h3>
{/each}
