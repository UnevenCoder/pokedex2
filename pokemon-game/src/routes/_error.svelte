<script>
	export let status;
	export let error;
	console.log(error)
	const dev = process.env.NODE_ENV === 'development';

</script>
<style>
main{
	width:70vw;
	height:80vh;
	display:flex;
	justify-content: center;
	align-items: center;
	margin-top:20vh;
	flex-direction:column;
}
h1{
	align-self:center;
 font-size:5rem;

}
h2{
	font-size:3rem;
	align-self:center;
}
</style>
<main>
<h1>Error Code : {status}</h1>
<h2><a href=".">Back to Homepage</a></h2>
</main>
