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
</style>


<Nav {segment}/>
<main>
	<slot></slot>
</main>
