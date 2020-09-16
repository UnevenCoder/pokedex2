<!--script context="module">
  import name from './Stats.svelte'
    export async function preload({ params, query }) {
  console.log(params)
      const res = await this.fetch(
       'https://pokeapi.co/api/v2/pokemon/'+name+'/'
      );
      const data = await res.json();
      if (res.status === 200) {
        return {
         da,
        };
      } else {
        this.error(res.status, data.message);
      }
    }

  </script>
<script>
export let name 

console.log(name,data)

</script>-->