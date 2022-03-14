<script>
    import TableHead from "./TableHead.svelte"
    export let isTableHead = true
    export let persons = [
    ]
</script>

{#if isTableHead}
<tr>
<TableHead/>
</tr>
{:else}
{#each persons as person}
<tr>
<td>{person.name}</td>
<td>{person.age}</td>
<td><img src={person.avatar} alt="faker image"></td>
</tr>
{/each}
{/if}
<style>    
    tr {
		border: 1px;
        border-color: black;
		border-style: solid;
	}
    td {
        border: 1px;
        border-color: black;
		border-style: solid;
    }
</style>


