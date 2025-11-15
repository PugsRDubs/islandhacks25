<script lang="ts">
    import type { TimerData } from "./Timer.svelte";
    import Timer from "./Timer.svelte";

    var timers : Array<TimerData> = $state([]);

    function a() {
        timers.push({ name: "Timer", time: 10, hidden: true});
    }

    function flip(bool : Boolean) {
        bool = !bool
    }
</script>

<h1>Tuff ahh timer</h1>
<button onclick={a}>abcd</button>
<h1>Problems:</h1>
<ul>
    {#each timers as timer, i}
        <Timer {timer} />
    {/each}
</ul>