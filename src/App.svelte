<script>
	import {faker} from "@faker-js/faker"
	export let name;
	import PeopleTable from "./components/PeopleTable.svelte"

	let persons = []
	for(let i = 0; i<10; i++) {
		generateNewPerson()
	}
	function generateNewPerson() {
		persons.push({
			name: faker.name.findName(),
			age: faker.datatype.number({'min': 10, 'max': 110}),
			avatar: faker.image.avatar()
		})
		persons = persons
    }

	function removeFirstPerson() {
		persons = [...persons].slice(1)
	}

	function sortByName() {
		persons.sort(function(a, b){
    		if(a.name < b.name) { return -1; }
    		if(a.name > b.name) { return 1; }
    	return 0;
		})
		persons = persons
	}

	function sortByAge() {
		persons.sort(function(a, b){
    		if(a.age < b.age) { return -1; }
    		if(a.age > b.age) { return 1; }
    	return 0;
		})
		persons = persons
	}
</script>

<main>
	<h1>Random people generated with {name}</h1>
	
	<button on:click={generateNewPerson}>Generate new person</button>
	<button on:click={removeFirstPerson}>Remove first person</button>
	<button on:click={sortByName}>Sort By Name</button>
	<button on:click={sortByAge}>Sort By Age</button>
	<PeopleTable persons={persons}/>
</main>

<style>
	
	button {
		margin-left: 45%;
		margin-right: 45%;
	}
	main {
		display: flex;
		flex-direction: column;
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>