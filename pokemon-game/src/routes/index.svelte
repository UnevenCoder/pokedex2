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
const keys = { 'electrode': 1    ,  'exeggcute': 2 , 'exeggutor': 3 ,
   'cubone': 4 ,        'marowak': 5 ,   'hitmonlee': 6 ,
   'hitmonchan': 7 ,    'lickitung': 8 ,   'koffing': 9 ,
   'weezing': 10,      'rhyhorn': 11 , 'rhydon': 12 ,
   'chansey': 13 ,      'tangela': 14 ,    'kangaskhan': 15 ,
   'horsea': 16 ,     'seadra': 17 ,     'goldeen': 18 ,
   'seaking': 19 ,      'staryu': 20 ,     'starmie': 21 ,
   'mr-mime': 22 ,      'scyther': 23 ,    'jynx': 24 ,
   'electabuzz': 25 ,   'magmar': 26 ,    'pinsir': 27 ,
   'tauros': 28 ,       'magikarp': 29 ,   'gyarados': 30 ,
   'lapras': 31 ,       'ditto': 32 ,      'eevee': 33 ,
   'vaporeon': 34 ,     'jolteon': 35 ,    'flareon': 36 ,
   'porygon': 37 ,     'omanyte': 38 ,    'omastar': 39 ,
   'kabuto': 40 ,      'kabutops': 41 ,   'aerodactyl': 42 ,
   'snorlax': 43 ,      'articuno': 44 ,   'zapdos': 45 ,
   'moltres': 46 ,      'dratini': 47 ,    'dragonair': 48 ,
   'dragonite': 49,   'mewtwo': 50 ,     'mew': 51 ,
   'chikorita': 52 ,    'bayleef': 53 ,    'meganium': 54 ,
   'cyndaquil': 55 ,    'quilava': 56 ,   'typhlosion': 57 ,
   'totodile': 58 ,     'croconaw': 59 ,   'feraligatr': 60 ,
   'sentret': 61 ,      'furret': 62 ,   'hoothoot': 63 ,
   'noctowl': 64 ,      'ledyba': 65 ,     'ledian': 66 ,
   'spinarak': 67 ,     'ariados': 68 ,    'crobat': 69 ,
   'chinchou': 70 ,     'lanturn': 71 ,    'pichu': 72 ,
   'cleffa': 73 ,       'igglybuff': 74 ,  'togepi': 75 ,
   'togetic': 76 ,      'natu': 77 ,     'xatu': 78 ,
   'mareep': 79 ,       'flaaffy': 80 ,    'ampharos': 81 ,
   'bellossom': 82 ,    'marill': 83 ,     'azumarill': 84 ,
   'sudowoodo': 85 ,    'politoed': 86 ,   'hoppip': 87 ,
   'skiploom': 88,     'jumpluff': 89 ,   'aipom': 90 ,
   'sunkern': 91 ,      'sunflora': 92 ,   'yanma': 93 ,
   'wooper': 94 ,      'quagsire': 95 ,   'espeon': 96 ,
   'umbreon': 97 ,      'murkrow': 98 ,    'slowking': 99 ,
   'misdreavus': 100} 


  let a = data.results , val='';
  $:if(val!='Search')fil()
  
  function fil(){a=data.results.filter(x=>x.name.includes(val))}
  </script>
  <input type='text' placeholder="Search a Pokemon's name and learn about it's stats" bind:value={val}>
  <div id='res'>

{#each a as ind,i}
<a href="/pokemon/{i+1}">
<div class='card'>

<img  src='https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/{keys[ind.name]}.png' alt='' />
<h1 >{ind.name}</h1>
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
justify-content: center;
align-items:center;
text-align:center;
}
img{
height:125px;
width:125px;
margin-top:-40px;

}
a{
  text-decoration: none;
}
h1{
	align-self:center;
	text-align:center;
  text-decoration: none;
  font-weight: 450;
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
  height:30px;
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
}

</style>