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

<h1>Active Tasks + Classes</h1>

{#each classes as name}
    <Class {name} />
{/each}

<hr>

<input bind:value={classInput} type="text" placeholder="Enter class...">
<button onclick={addClass}>Add class</button>
