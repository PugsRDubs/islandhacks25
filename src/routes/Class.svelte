<script lang="ts">
    import type { TimerData } from "./Timer.svelte";
    import Timer from "./Timer.svelte";

    var timers : Array<TimerData> = $state([]);

    function a() {
        timers.push({ name: "Timer", time: 10, hidden: true});
    }
</script>

<h1>English</h1>
<button onclick={a}>abcd</button>
<ul>
    {#each timers as timer, i}
        <Timer {timer} />
    {/each}
</ul>