<script context="module">
    export async function preload({ params, query }) {
  
      const res = await this.fetch(
        `https://pokeapi.co/api/v2/pokemon?offset=100&limit=100`
      );
      const data = await res.json();
      if (res.status === 200) {
        return {
         data,
        };
      } else {
        this.error(res.status, data.message);
      }
    }
  </script>
  
  <script>
  export let data;
  </script>
  <h3>Some famous Pokemons :)</h3>	
  <div id='res'>

{#each data.results as ind,i}
<div class='card'>
<img src='https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/{i+1}.png' alt='' />
<h1 >{ind.name}</h1>
</div>
{/each}
</div>
<style>
:global(.card){
width:200px;
height: 200px;
background-color:white;
flex-wrap: wrap;
margin-top:20px;
margin-left:20px; ;
margin-right:5px;
border-radius:20px;
box-shadow: 0 2px 5px rgba(0,0,0,.26);
display:flex;
flex-direction:column;
justify-content: center;
align-items:center;
text-align:center;
}
img{
height:150px;
width:150px;
margin-top:-40px;

}
h1{
	align-self:center;
	text-align:center;
}
#res{
	width:100%;
	height:auto;
	display: flex;
	justify-content:space-around;
	flex-wrap:wrap;
}
h3{
	font-size:3.5rem;
	color:white;
	text-align:center;
	
}
</style>