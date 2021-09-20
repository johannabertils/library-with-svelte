<script>
    import { onMount } from "svelte";

    export let Series = [];

    onMount(() => {
        fetch("http://localhost:3000/series")
            .then((res) => res.json())
            .then((data) => {
                console.log("data", data);
                Series = data;
            });
    });
</script>

<div>
    {#each Series as Serie}
        <div>
            <ul>
                <li>
                    {Serie.title} 
                   <p>{Serie.about}</p> 
                </li>
            </ul>
        </div>
    {:else}
        <div>Hämtar data</div>
    {/each}
</div>

<style>
    div{
        text-align: center;
		padding: 1em;
		max-width: 300px;
		margin: 0 auto;
    }
    
    ul {
        list-style-type: none;
        max-width: 300px;
    }

    li {
        font-size: 20px; 
    }
    p {
        font-size: 12px; 
        
    }
</style>
