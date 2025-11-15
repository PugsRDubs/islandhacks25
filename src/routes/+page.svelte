<script lang="ts">
    import Class from "./Class.svelte";

    let classes : Array<String> = $state([])

    let classInput = $state("");

    function addClass() {
        if (classInput == "") {
            alert(`Name the class!`);
        }
        else {
            classes.push(classInput);
            classInput = "";
        }
    }
    
</script>

<h1>Tuff ahh timer</h1>
<input bind:value={classInput} type="text">
<button onclick={addClass}>Add class</button>
{#each classes as name}
    <Class {name} />
{/each}