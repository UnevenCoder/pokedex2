<script>
export let segment
</script>

<style>

header{
    background-color: #ef5350;
    color: #fff;
    padding: 4px 4px 0;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1;
    box-shadow: 0 2px 5px rgba(0,0,0,.26);
	height:15vh;	
     display:flex;
     align-items: center;
     justify-content: center;
     text-align:center;
     }

     h1 {
    margin-top: 17px;
    margin-right: auto;
    font-size: 3em;
     }
     nav{

          width:400px;
       
     }
     ul{
          display:flex;
          width:100%;
          justify-content:space-evenly;   
          list-style: none;
          font-size: large;
          text-decoration:none;
     }
</style>
<header>


       <h1> Pokedex 2.0 </h1>
{#if segment != undefined}
<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'home' : undefined}" href=".">Home</a></li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen-->
	</ul>
</nav>
{/if}
</header>