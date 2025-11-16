<script lang="ts" module>
    export type TimerData = {
        name: string;
        time: number;
    };
</script>

<script lang="ts">
    import { fade, slide } from "svelte/transition";

    const audio = new Audio('/ringtone.mp3');

    let { timer, destroyTimer } = $props();

    let seconds: number = $state(timer.time);

    let counting = $state(false);

    let date = new Date;

    const makeIteration = (): void => {
        if (seconds > 1) {
            if (counting) {
                setTimeout(makeIteration, 1000); // 1 second waiting
            }
        }
        if (counting) {
            seconds -= 1;
        }
        if (seconds == 0) {
            audio.play();
            alert(`Time is up!`);
            
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

    function getSeconds(s: number) {
        if (isNaN(seconds) || seconds < 0) return '00:00:00';

        let minuteTime = Math.floor(s / 60);
        let hourTime = Math.floor(minuteTime / 60);

        s %= 60;
        minuteTime %= 60;

        return (
            `${hourTime.toString().padStart(2, '0')}:` +
            `${minuteTime.toString().padStart(2, '0')}:` +
            `${s.toString().padStart(2, '0')}`
        );
    };
    
</script>

<div transition:slide>
    <button onclick={() => console.log(date.getDate())}>date</button>

    <button onclick={() => timerClicked()}>
        {#if counting}
            <strong>
                {timer.name} - {getSeconds(seconds)}
            </strong>
        {:else}
            {timer.name} - {getSeconds(seconds)}
        {/if}
    </button>
    <button onclick={destroyTimer}>Finish</button>
    {#if seconds != timer.time || counting}
    <button transition:fade onclick={reset}>reset</button>
    <meter transition:fade value={timer.time - seconds} max={timer.time}></meter>
    {/if}
    <br>
</div>

<style>
    button {
        margin-top: 10px;
    }
    meter {
        width: 50%;
    }
</style>
