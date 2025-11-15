<script lang="ts">
    interface Timer {
        name: string;
        time: number;
        hidden: Boolean;
    }

    var timers : Array<Timer> = $state([]);

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
        <li>timer</li>
        <button onclick={() => timers[i].hidden = !timer.hidden}>{#if timer.hidden}show{:else}hide{/if}</button>
        {#if !timer.hidden}
            <p>{timer.time}</p>
        {/if}
    {/each}
</ul>