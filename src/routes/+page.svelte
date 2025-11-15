<script lang="ts">
    var timers : Array<String> = $state([]);

    function a() {
        timers.push("a");
    }
</script>

<h1>Tuff ahh timer</h1>
<h1>Problems:</h1>
<ul>
    {#each timers as timer}
        <li>{timer}</li>
    {/each}
</ul>
<button onclick={a}>abcd</button>