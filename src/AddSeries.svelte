<script>
    export let name = "";
    export let about = "";

    $: console.log(name);

    const onSubmit = (event) => {
        event.preventDefault();
        console.log("click", event.target.about.value);
        const key = Math.random();
        let newSerie = {
            id: key,
            title: event.target.name.value,
            about: event.target.about.value,
        };


        fetch("http://localhost:3000/series", {
            method: "post",
            headers: {
                "content-type": "application/json",
            },
            body: JSON.stringify(newSerie),
        })
            .then((res) => res.json())
            .then((data) => console.log("success", data))
            .catch((err) => console.log("error", err));
    };
</script>

<form on:submit={onSubmit}>
    <input type="text" id="name" bind:value={name} />
    <input type="text" id="about" bind:value={about} />
    <button>Save</button>
</form>

<style>
</style>
