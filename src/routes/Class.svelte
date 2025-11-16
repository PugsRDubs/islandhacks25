<script lang="ts">
    import type { TimerData } from "./Timer.svelte";
    import Timer from "./Timer.svelte";
    import { slide } from "svelte/transition";

    let { name, color } = $props();

    let timers : Array<TimerData> = $state([]);

    let taskName = $state("");
    let taskHours = $state(0);
    let taskMinutes = $state(0);

    function add_timer() {
        if (taskHours > 23 || taskHours < 0) {
            alert(`Invalid hours!`);
        }
        else if (taskMinutes > 59 || taskMinutes < 0) {
            alert(`Invalid minutes!`);
        }
        else {
            let fullTime = taskHours * 3600 + taskMinutes * 60;
            if (fullTime <= 0) {
                alert(`Invalid time!`);
            }
            else {
                timers.push({ name: taskName, time: fullTime, hidden: true});
                taskName = "";
                taskHours = 0;
                taskMinutes = 0;
            }
        }
        
    }
</script>

<div transition:slide style="--color: {color}">
    <h1>{name}</h1>



<input bind:value={taskName} type="text" placeholder="task name">
<input bind:value={taskHours} type="number" placeholder="HH" min="0" max="23">
<span>:</span>
<input bind:value={taskMinutes} type="number" placeholder="MM" min="0" max="59">
<button onclick={add_timer}>Add task</button>

{#each timers as timer, i}
    <Timer {timer} destroyTimer={() => timers.splice(i, 1)} />
{/each}

</div>

<style>
    div {
        background-color: var(--color);
        padding: 20px;
        border-radius: 10px;
        margin-bottom: 20px;
    }
</style>