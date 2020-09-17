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
export let post;
let arr=[]
console.log(post.types.length,post.types[0].type.name)
for(let i = 0;i<post.types.length;i++){
arr.push(post.types[i].type.name)
}
</script>

<svelte:head>
<title>{post.forms[0].name}</title>
</svelte:head>
<main id='main'>
<div id='top'>
	<button type="button" aria-label="close modal" title="close modal" class="ngx-modal__close-btn ngx-modal-closable-target"><span class="ngx-modal__icon-close ngx-modal-closable-target">×</span></button>
</div>
<div id='mid'>
<img src={post.sprites.front_default} alt='' />
<div class='content'>
	<h3>{post.name}</h3>
	{#if arr != []}
{#each arr as a}
<h4>{a}</h4>
{/each}
{/if}
</div>
</div>
</main>




<style>
	h3 {
    display: block;
    font-size: 2em;
    margin-block-start: 0.67em;
    margin-block-end: 0.67em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
    font-weight: bold;
}
#mid{
	display: flex;
    margin-top: 0;
    width: 60vw;
    height: auto;
    align-items: center;
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

	.content :global(ul) {
		line-height: 1.5;
	}

	.content :global(li) {
		margin: 0 0 0.5em 0;
	}
	:global(img){
		transform: scale(2);
    	margin: 30px auto;
	}
	:global(#top){
	    margin-bottom: auto;
    height: 50px;
    background-color: #ef5350;
    width: 60vw;
     }
	span{
		margin-top:16vh;
		color:white;
		background-color: initial;
	}
	#main{
		margin-top:17vh;
		margin-left:20vw;
		margin-right: 20vw;
		left:0;right:0;
		top:0;
		height:80vh;
		width:60vw;
		background-color: white;

	}
	.ngx-modal__close-btn {
    text-decoration: none;
	margin-top:17vh;
	margin-right:21vw;
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
}
</style>

