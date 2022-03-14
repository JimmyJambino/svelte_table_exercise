<script>
    import TableRow from "./TableRow.svelte"
    export let persons = [
    ]    
</script>

<table>
    <TableRow/>
    <TableRow isTableHead={false} persons={persons}/>
</table>

<style>
    table {
        border: 2px;
		border-color: black;
		border-style: solid;
    }
</style>