<script lang="ts">
    var timers : Array<Boolean> = $state([]);

    function a() {
        timers.push(false);
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
        <button onclick={() => timers[i] = !timer}>{#if timer}hide{:else}show{/if}</button>
        {#if timer}
            <p>hey</p>
        {/if}
    {/each}
</ul>