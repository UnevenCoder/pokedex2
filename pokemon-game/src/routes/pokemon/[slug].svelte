<script context="module">
	export async function preload({ params, query }) {
		// the `slug` parameter is available because
		// this file is called [slug].svelte
		const res = await this.fetch(`https://pokeapi.co/api/v2/pokemon/${params.slug}/`);
		const data = await res.json();
         
		if (res.status === 200) {
			return { post: data };
		} else {
			this.error(res.status, data.message);
		}
	}
</script>

<script>
import { prop_dev } from "svelte/internal";

export let post;
let arr=[]

for(let i = 0;i<post.types.length;i++){
arr.push(post.types[i].type.name)
}
let desc = ["For some time after its birth it grows by gaining nourishment from the seed on its back." ,
   "When the bud on its back starts swelling a sweet aroma wafts to indicate the flowers coming bloom." ,"After a rainy day the flower on its back smells stronger. The scent attracts other Pokémon." , "The fire on the tip of its tail is a measure of its life. If healthy its tail burns intensely.","In the rocky mountains where Charmeleon live their fiery tails shine at night like stars." 
,"It is said that Charizards fire burns hotter if it has experienced harsh battles." 
,"It shelters itself in its shell then strikes back with spouts of water at every opportunity." 
,"It is said to live  years. Its furry tail is popular as a symbol of longevity." 
,"The jets of water it spouts from the rocket cannons on its shell can punch through thick steel." 
,"It releases a stench from its red antenna to repel enemies. It grows by molting repeatedly." 
  , "A steel-hard shell protects its tender body. It quietly endures hardships while awaiting evolution." 
 , "It loves the honey of flowers and can locate flower patches that have even tiny amounts of pollen." 
  , "It eats its weight in leaves every day. It fends off attackers with the needle on its head." 
 ,"While awaiting evolution it hides from predators under leaves and in nooks of branches." 
  , "Its best attack involves flying around at high speed striking with poison needles then flying off." 
  , "It is docile and prefers to avoid conflict. If disturbed however it can ferociously strike back." 
,"It flies over its wide territory in search of prey downing it with its highly developed claws." 
 ,"It flies over its wide territory in search of prey downing it with its highly developed claws." 
   ,"It searches for food all day. It gnaws on hard objects to wear down its fangs which grow constantly during its lifetime." 
  , "With its long fangs this surprisingly violent Pokémon can gnaw away even thick concrete with ease." 
  , "It flaps its small wings busily to fly. Using its beak it searches in grass for prey." 
, "It has the stamina to fly all day on its broad wings. It fights by using its sharp beak." 
  , "It sneaks through grass without making a sound and strikes unsuspecting prey from behind." 
  ,"they are frozen in fear." 
  ,"It occasionally uses an electric shock to recharge a fellow Pikachu that is in a weakened state." 
 , "Its tail discharges electricity into the ground protecting it from getting shocked." 
,"It digs deep burrows to live in. When in danger it rolls up its body to withstand attacks." 
 ,"The spikes on its body are made up of its hardened hide. It rolls up and attacks foes with its spikes." 
   , "While it does not prefer to fight even one drop of the poison it secretes from barbs can be fatal." 
  , "When it senses danger it raises all the barbs on its body. These barbs grow slower than Nidorinos." 
 ,  "Its entire body is armored with hard scales. It will protect the young in its burrow with its life." 
    ,   "It scans its surroundings by raising its ears out of the grass. Its toxic horn is for protection." 
 , "It has a violent disposition and stabs foes with its horn which oozes poison upon impact." 
   ,  "One swing of its mighty tail can snap a telephone pole as if it were a matchstick." 
,  "On nights with a full moon Clefairy gather from all over and dance. Bathing in moonlight makes them float." 
   ,   "Their ears are sensitive enough to hear a pin drop from over a mile away so theyre usually found in quiet places." 
  ,    "As each tail grows its fur becomes more lustrous. When held it feels slightly warm." 
  ,   "Each of its nine tails is imbued with supernatural power and it can live for a thousand years." 
,    "Looking into its cute round eyes makes it start singing a song so pleasant listeners cant help but fall asleep." 
  ,  "Its fine fur feels so pleasant those who accidentally touch it cannot take their hands away." 
  ,  "It does not need eyes because it emits ultrasonic waves to check its surroundings while it flies." 
  ,   "Flitting around in the dead of night it sinks its fangs into its prey and drains a nearly fatal amount of blood." 
 ,     "It often plants its root feet in the ground during the day and sows seeds as it walks about at night." 
   ,   "The honey it drools from its mouth smells so atrocious it can curl noses more than a mile away." 
    ,   "Its petals are the largest in the world. As it walks it scatters extremely allergenic pollen." 
 ,    "Mushrooms named tochukaso grow on its back. They grow along with the host Paras." 
   ,   "A mushroom grown larger than the hosts body controls Parasect. It scatters poisonous spores." 
  ,     "Its big eyes are actually clusters of tiny eyes. At night its kind is drawn by light." 
    ,"It flutters its wings to scatter dustlike scales. The scales leach toxins if they contact skin." 
    ,   "A Pokémon that lives underground. Because of its dark habitat it is repelled by bright sunlight." 
  ,    "Its three heads move alternately driving it through tough soil to depths of over  miles." 
   ,   "It is nocturnal in nature. If it spots something shiny its eyes glitter brightly." 
 ,"A very haughty Pokémon. Among fans the size of the jewel in its forehead is a topic of much talk." 
  ,  "When headaches stimulate its brain cells which are usually inactive it can use a mysterious power." 
,   "When its forehead shines mysteriously Golduck can use the full extent of its power." 
,    "It lives in treetop colonies. If one becomes enraged the whole colony rampages for no reason." 
,     "It grows angry if you see its eyes and gets angrier if you run. If you beat it it gets even madder." 
,    "Extremely loyal to its Trainer it will bark at those who approach the Trainer unexpectedly and run them out of town." 
,    "The sight of it running over  miles in a single day and night has captivated many people." 
,     "Its skin is so thin its internal organs are visible. It has trouble walking on its newly grown feet." 
,    "The spiral pattern on its belly subtly undulates. Staring at it gradually causes drowsiness." 
,    "With its extremely tough muscles it can keep swimming in the Pacific Ocean without resting." 
,     "Using its psychic power is such a strain on its brain that it needs to sleep for  hours a day." 
,    "It stares at its silver spoon to focus its mind. It emits more alpha waves while doing so." 
   ,     "The spoons clutched in its hands are said to have been created by its psychic powers." 
 ,   "Though small in stature it is powerful enough to easily heft and throw a number of Geodude at once." 
  ,    "It happily carries heavy cargo to toughen up. It willingly does hard work for people." 
   ,     "Its four muscled arms slam foes with powerful punches and chops at blinding speed." 
 ,   "It prefers hot and humid environments. It is quick at capturing prey with its vines." 
   ,  "A Pokémon that appears to be a plant. It captures unwary prey by dousing them with a toxic powder." 
   ,    "It pools in its mouth a fluid with a honey-like scent which is really an acid that dissolves anything." 
   ,    "Because its body is almost entirely composed of water it shrivels up if it is washed ashore." 
  ,     "It extends its  tentacles to form an encircling poisonous net that is difficult to escape." 
 ,    "At rest it looks just like a rock. Carelessly stepping on it will make it swing its fists angrily." 
    ,     "It rolls on mountain paths to move. Once it builds momentum no Pokémon can stop it without difficulty." 
    ,    "Even dynamite cant harm its hard boulder-like body. It sheds its hide just once a year." 
,   "As a newborn it can barely stand. However through galloping its legs are made tougher and faster." 
  ,    "When at an all-out gallop its blazing mane sparkles enhancing its beautiful appearance." 
  ,    "Although slow it is skilled at fishing with its tail. It does not feel pain if its tail is bitten." 
,     "Though usually dim witted it seems to become inspired if the Shellder on its tail bites down." 
,    "The electromagnetic waves emitted by the units at the sides of its head expel antigravity which allows it to float." 
   ,    "The stronger electromagnetic waves from the three linked Magnemite are enough to dry out surrounding moisture." 
,    "It cant live without the stalk it holds. Thats why it defends the stalk from attackers with its life." 
,    "The brains in its two heads appear to communicate emotions to each other with a telepathic power." 
   ,    "When Doduo evolves into this odd breed one of its heads splits into two. It runs at nearly  mph." 
  ,    "The colder it gets the better it feels. It joyfully swims around oceans so cold that they are filled with floating ice." 
,   "Its streamlined body has low resistance and it swims around cold oceans at a speed of eight knots." 
,   "Born from sludge these Pokémon now gather in polluted places and increase the bacteria in their bodies." 
,    "Its so stinky! Muks body contains toxic elements and any plant will wilt when it passes by." 
,    "It swims backward by opening and closing its two shells. Its large tongue is always kept hanging out." 
,    "It fights by keeping its shell tightly shut for protection and by shooting spikes to repel foes." 
,    "Born from gases anyone would faint if engulfed by its gaseous body which contains poison." 
,     "It likes to lurk in the dark and tap shoulders with a gaseous hand. Its touch causes endless shuddering." 
,   "The leer that floats in darkness belongs to a Gengar delighting in casting curses on people." 
,    "Opening its large mouth it ingests massive amounts of soil and creates long tunnels." 
,    "It can tell what people are dreaming by sniffing with its big nose. It loves fun dreams." 
 ,     "Seeing its swinging pendulum can induce sleep in three seconds even in someone who just woke up." 
,   "It lives in burrows dug on sandy beaches. Its pincers fully grow back if they are broken in battle." 
  ,    "The larger pincer has - horsepower strength. However it is so heavy it is difficult to aim." 
,"It looks just like a Pok Ball. It is dangerous because it may electrocute or explode on contact." ]

  let bool = false
  $:{
	  if(bool==true){
		document.getElementById("img").src=post.sprites.front_shiny_female
		
	  }
  }
  let total = 0
  for(let i = 0;i<post.stats.length;i++){
total+=post.stats[i].base_stat
  }
  let abi = []
  for(let i = 0;i<post.abilities.length;i++){
abi.push(post.abilities[i].ability.name)
  }
  
</script>

<svelte:head>
<title>{post.forms[0].name}</title>
</svelte:head>

<main id='main'>
<div id='mid'>
<div class='content'>
	<h1>{post.name}</h1>
{#if arr != []}
<div id='ms'>
{#each arr as a}
<h3 class='sy'>{a}</h3>
{/each}
</div>
{/if}
<h2 class='a'><b>Height</b>: {post.height/10}m</h2>
<h2 class='a'> <b>Weight</b>: {post.weight/10}kg</h2>
<h2 class="a"><b>Abilities </b> {abi}</h2>
<h2 class="a"><b>Stats :</b></h2>
{#each post.stats as s}
<div class='sm'>
<h3 class='a'><b>{s.stat.name}</b></h3> <progress class="progress" value={s.base_stat} max="100"> {s.base_stat} </progress>
</div>
{/each}
<h2 class="a"><b>Total :</b> {total}</h2>
<h2 class='a'><i>{desc[post.id-1]}</i></h2>
</div>
<img id='img' on:hover={()=>bool = true} src={post.sprites.front_shiny} alt='' />
</div>
</main>




<style>
#ms{
	display:flex
}
.sm{
	display:flex;
	width:400px;
	justify-content:space-between
}
	h2 {
		text-transform: capitalize;
    display: block;
    font-size: 2em;
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}

.sy
	{
	padding:4px;
	background-color:tomato;
	color:white;
	text-align:center;
	margin-left:5px;
    
}

#mid{
	display: flex;
    margin-top: 0;
    width: 80vw;
    height: auto;
    align-items: center;
	margin-bottom:auto;
	justify-content:space-evenly
}
.content{
	margin-right:auto;
	margin-left:30px;
}
	/*
		By default, CSS is locally scoped to the component,
		and any unused styles are dead-code-eliminated.
		In this page, Svelte can't know which elements are
		going to appear inside the {{{post.html}}} block,
		so we have to use the :global(...) modifier to target
		all elements inside .content
	*/
	.content :global(h2) {
		font-size: 1.4em;
		font-weight: 500;
	}

	.content :global(pre) {
		background-color: #f9f9f9;
		box-shadow: inset 1px 1px 5px rgba(0,0,0,0.05);
		padding: 0.5em;
		border-radius: 2px;
		overflow-x: auto;
	}
	:global(.body){
		margin:0;
		display:flex;
		justify-content: center;
		align-items: center;
	}	

	.content :global(pre) :global(code) {
		background-color: transparent;
		padding: 0;
	}



	.content :global(li) {
		margin: 0 0 0.5em 0;
	}
img{
		transform: scale(2.5);
		margin-bottom:auto;
		margin-right:15vw;
	}
	:global(#top){
	    margin-bottom: auto;
    height: 50px;
    background-color: #ef5350;
    width: 70vw;
     }

	#main{
		margin-top:17vh;
		margin-left:15vw;
		margin-right: 15vw;
		left:0;right:0;
		top:0;
		height:800px;
		width:70vw;
		background-color: white;

	}
	@media only screen and (max-width: 600px) {
		
		#main{
		width:100vw;
		height:100vh;
		margin-left:0;
		margin-right: 0;
		margin-top:0;
	}
	:global(#top){
		margin-left:auto;
		margin-top:0;
    height: 50px;
    background-color: #ef5350;
    width: 100vw;
     }

	#mid{
	display: flex;
  
    width: 100%;
    height: auto;
    align-items: center;
	margin-bottom:auto;
	overflow:hidden;
	justify-content:space-evenly;
	flex-direction:column-reverse;
}
.content{
	padding-top:30px;
	margin-left:0;
	padding-bottom:30px;

}
.sm{
	display:flex;
	width:350px;
	justify-content:space-between
}
img{
	margin-top:30px;
}
	}
	@media only screen and (min-width: 800px) {
		:global(.body){
		margin:0;
		display:flex;
		justify-content: center;
		flex-direction: column;
		align-items: center;
	}	

  img{
	transform: scale(3);
		margin-bottom:auto;
		margin-right:15vw;
  }
  .content{
	margin-right:auto;
	margin-left:60px;
}
}
@media only screen and (min-width: 1000px) {
  img{
	transform: scale(3.5);
	margin-top:30px;
		margin-bottom:auto;
		margin-right:15vw;
  }
  .content{
	margin-right:auto;
	margin-left:90px;
}
}
@media only screen and (min-width: 1200px) {
  img{
	transform: scale(4);
		margin-bottom:auto;
		margin-right:15vw;
  }
  .content{
	margin-right:auto;
	margin-left:100px;
}
}
	/*.ngx-modal__close-btn {
    text-decoration: none;
	margin-top:13vh;
	margin-right:14vw;
    display: block;
    padding: 4px 14px;
    font-size: 30px;
    border: 0;
    cursor: pointer;
    position: absolute;
    top: 0;
    right: 0;
	background-color: transparent;
	color: #2d2d2d;
	height:40px;
	margin-top:25vh;}
span{
	margin-top:-1vh;
	font-size:3rem;
}*/
</style>

