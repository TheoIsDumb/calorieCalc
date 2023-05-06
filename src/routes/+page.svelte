<script lang="ts">
    import Count from './components/count.svelte';
    import GenderSelect from './components/genderSelect.svelte';
    import ActivityLevelSelect from './components/activityLevelSelect.svelte';
    import NumInput from './components/numInput.svelte';

    let age:number;
    let weight:number;
    let height:number;
    let gender:string;
    let activity_level:string;

    const labels = ["Age (15-80)", "Weight (kg)", "Height (cm)"];

    $: bmr = (weight * 10) + (height * 6.25) - (age * 5) || 0;
    $: bmr_men = bmr + 5;
    $: bmr_women = bmr - 161;
</script>

<style>
    main {
        width: 98%;
        max-width: 520px;
    }

    .bottom {
        text-align: center;
    }

    .grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 0.5rem;
    }
</style>

<main>
    <h1>calorieCalc</h1>

    <GenderSelect bind:gender={gender}/>

    <NumInput bind:value={age} label={labels[0]}/>

    <div class="grid">
        <NumInput bind:value={weight} label={labels[1]}/>
        <NumInput bind:value={height} label={labels[2]}/>
    </div>

    <ActivityLevelSelect bind:activity_level={activity_level}/>

    {#if bmr != 0}
        <Count {activity_level} {bmr_women} {bmr_men} {gender}/>
    {:else}
        <h1 style="visibility: hidden">test</h1>
    {/if}


    <div class="bottom">
        <a href="https://git.vkdbois.xyz/theo/calorieCalc"
        target="_blank" rel="noopener noreferrer">
            source code
    </a> | 
        made by <a href="https://vkdbois.xyz" target="_blank" rel="noopener noreferrer">vkdbois.xyz</a>
    </div>
</main>