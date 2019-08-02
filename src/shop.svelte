<script>
    export let arr;
    let countTot = 0;
    let priceTot = 0
    function add(item) {
        item.count++;
        arr = arr;
        countTot = arr.reduce((prev,next) => {
            return prev + next.count
        },0);
        priceTot = arr.reduce((prev,next) => {
            return prev + next.count*next.price
        },0);
    }
</script>
<style>
dl{
    display: flex
}
dd{
    display:flex;
    flex-direction: column
}
</style>
总数：{countTot} <br />
总价：{priceTot}
{#each arr as item}
    <dl>  
        <dt>
            <img src={item.img} alt="">
        </dt>
        <dd>
            <span>{item.title}</span>
            <span>价格：{item.price}</span>
            <p><button>-</button><span>{item.count}</span><button on:click={() => add(item)}>+</button></p>
        </dd>  
    </dl>
{/each}
