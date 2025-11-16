<script lang="ts">
    import Class from "./Class.svelte";

    let classes : Array<String> = $state([])

    let classInput = $state("");

    let classColor = "#8d9b88";

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


{#each classes as name}
    <Class {name} color={classColor}/>
{/each}

<h1>Add a class</h1>
<input bind:value={classInput} type="text" placeholder="Enter class...">
<button onclick={addClass}>Add class</button>
<select bind:value={classColor} name="color" id="">
    <option value="#cf9999">Red</option>
    <option value="#dbb079">Orange</option>
    <option value="#e6c98c">Yellow</option>
    <option selected value="#8d9b88">Green</option>
    <option value="#93aacf">Blue</option>
    <option value="#ae97c9">Lavender</option>
</select>
