<script>

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
     svg{
          align-self:flex-start;
          margin-right:auto;
          margin-top:17px;
     }
     h1 {
    margin-top: 17px;
    margin-right: auto;
    font-size: 3em;
     }
</style>
<header>
     <svg width="2.5em" height="2.5em" viewBox="0 0 16 16" class="bi bi-list" fill="currentColor" xmlns="http://www.w3.org/2000/svg">
          <path fill-rule="evenodd" d="M2.5 11.5A.5.5 0 0 1 3 11h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4A.5.5 0 0 1 3 7h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5zm0-4A.5.5 0 0 1 3 3h10a.5.5 0 0 1 0 1H3a.5.5 0 0 1-.5-.5z"/>
        </svg>

       <h1> Pokedex </h1>
</header>
<!--
<nav>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">home</a></li>
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">about</a></li>

		<!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen
		<li><a rel=prefetch aria-current="{segment === 'blog' ? 'page' : undefined}" href="blog">blog</a></li>
	</ul>
</nav>
-->