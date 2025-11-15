<script lang="ts" module>
    export type TimerData = {
        name: string;
        time: number;
        hidden: Boolean;
    };
</script>

<script lang="ts">
    let { timer } = $props();
</script>

<li>timer</li>
<button onclick={() => timer.hidden = !timer.hidden}>{#if timer.hidden}show{:else}hide{/if}</button>
{#if !timer.hidden}
    <p>{timer.time}</p>
{/if}