<script>
	export let name;
	import Shop from './shop.svelte';
	import { onMount } from 'svelte'
    let arr = []
    onMount(async function(){
        let res = await fetch('http://localhost:7001/shop');
        let result = await res.json();
		arr = result.list;   
    })
</script>

<style>
	h1 {
		color: purple;
	}
</style>
<h1>Hello {name}!</h1>
<Shop {arr}/>

