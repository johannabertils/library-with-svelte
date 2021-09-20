<script>
    import { onMount } from "svelte";
    import Serie from "./Serie.svelte";

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
    ul {
        list-style-type: none;
    }
    li {
        font-size: 20px; 
    }
    p {
        font-size: 12px; 
    }
</style>
