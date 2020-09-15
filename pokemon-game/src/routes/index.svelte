<script>
fetch('https://pokeapi.co/api/v2/pokemon?offset=100&limit=100')
.then(res=>res.json)
.then(data=>console.log(data))
</script>
<main>
<h3>All the Pokemon out there :)</h3>
</main>

<style>

main{
	margin-top:17vh;
}
</style>