<svelte:head>
  <title>Home</title>
</svelte:head>
<script context="module">
  /*  export async function preload({ params, query }) {
  
      const res = await this.fetch(
        `https://pokeapi.co/api/v2/pokemon?offset=200&limit=100`
      );
      const da = await res.json();
    
      const data = await da.results.map((x,i)=>{
        let id = i + 1;
        return {name:x.name,id:id,src:'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/'+id+'.png'}
      })

      if (res.status === 200) {
        return {
         data
        };
      } else {
        this.error(res.status, data.message);
      }
    }
*/
  </script>
  
  <script>
    import {apidata } from './pokemon/data.js'

  let a = apidata , val='';
  $:if(val!='Search')fil()
  
  function fil(){a=apidata.filter(x=>x[0].includes(val))}
  </script>

  <input type='text' placeholder="Search a Pokemon's name and learn about it's stats" bind:value={val}>
  <div id='res'>

{#each a as data,i}
<a href="/pokemon/{i+1}">
<div class='card'>

<img  src='{data[2]}' alt={data[0]} />
<h1 >{data[0]}</h1>
</div>
</a>
{/each}
</div>


<style>
:global(.card){
width:250px;
height: 250px;
background-color:white;
flex-wrap: wrap;
margin-top:20px;
margin-left:20px; ;
margin-right:5px;
border-radius:20px;
box-shadow: 0 2px 5px rgba(0,0,0,.26);
display:flex;
flex-direction:column;
justify-content: space-evenly;
align-items:center;
text-align:center;
}
img{
max-height:150px;
max-width:150px;
margin-top: 35px;

}
a{
  text-decoration: none;
}
h1{
	align-self:center;
	text-align:center;
  text-decoration: none;
  font-weight: 450;
  top: 80px;
}
#res{
	width:100%;
	height:auto;
	display: flex;
	justify-content:space-evenly;
  align-items :flex-start;
	flex-wrap:wrap;
}
input{
  border:2px solid snow ;
  background-color:transparent;
  width:75vw;
  height:60px;
color:white;
margin-right:12.5vw;
margin-left:12.5vw;
margin-top:5vh;
margin-bottom:5vh;
}
::placeholder{
color:white;
text-align:center;
color:aquamarine;

font-size: 2em;
}

</style>