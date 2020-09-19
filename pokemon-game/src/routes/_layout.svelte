<script>
	import Nav from '../components/Nav.svelte';
	export let segment;

</script>

<style>
:global(main){
	margin-right: auto;
	margin-top:17vh;
	width:100%;
	height:auto;
	display:flex;
	justify-content:center;
	flex-direction: column;
	background-color:gray;
}
section{
    /* width: 100vw; */
    /* height: 5vh; */
    margin-top: 50px;
    /* background-color: white; */
    /* color: tomato; */
    text-align: center;

}
h5{
	font-size:2rem;
}
</style>


<Nav {segment}/>
<main>
	<slot></slot>
<section>
	<h5>Made by Ameen :)</h5>
</section>
</main>