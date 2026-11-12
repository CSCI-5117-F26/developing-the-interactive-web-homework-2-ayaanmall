<script>

    let catfact = $state("Old boring fact")

    async function new_fact() {
        const fetched_fact = await fetch("https://catfact.ninja/fact")
        if (fetched_fact.ok) {
            const data = await fetched_fact.json()
            catfact = data.fact
        }
    }
</script>

<p>{catfact}</p>
<button onclick={new_fact}>New Fact!</button>