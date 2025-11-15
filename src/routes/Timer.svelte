<script lang="ts" module>
    export type TimerData = {
        name: string;
        time: number;
        hidden: Boolean;
    };
</script>

<script lang="ts">
    let { timer } = $props();

    let seconds: number = $state(timer.time);

    let counting = $state(false);

    const makeIteration = (): void => {
        if (seconds > 1) {
            if (counting) {
                setTimeout(makeIteration, 1000); // 1 second waiting
            }
        }
        if (counting) {
            seconds -= 1;
        }
    };

    function timerClicked() {
        if (counting) {
            counting = false;
        }
        else {
            counting = true;
            setTimeout(makeIteration, 1000);
        }
    }

    function reset() {
        counting=false; 
        seconds=timer.time;
    }
    
</script>

<button onclick={() => timerClicked()}>{#if counting}pause{:else}start{/if}</button>
<button onclick={() => timer.hidden = !timer.hidden}>{#if timer.hidden}show{:else}hide{/if}</button>
{#if seconds != timer.time || counting}
<button onclick={reset}>reset</button>
{/if}
{#if !timer.hidden}
    <p>{seconds}</p>
{/if}

<style></style>