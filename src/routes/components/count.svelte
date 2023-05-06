<script lang="ts">
    export let gender:string;
    export let activity_level:string;
    export let bmr_men = 1;
    export let bmr_women = 1;

    const activity_levels: { [key: string]: number } = {
        "BMR": 1,
        "Sedentary": 1.2,
        "Lightly Active": 1.375,
        "Moderately Active": 1.55,
        "Very Active": 1.725,
        "Extra Active": 1.9
    }
</script>

{#if gender == "Male"}
    <h1>{bmr_men * activity_levels[activity_level]}</h1>
{:else if gender == "Female"}
    <h1>{bmr_women * activity_levels[activity_level]}</h1>
{/if}