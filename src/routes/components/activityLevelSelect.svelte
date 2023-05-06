<script lang="ts">
    export let activity_level:String;
    const activity_level_options = ["BMR", "Sedentary", "Lightly Active", "Moderately Active", "Very Active", "Extra Active"];
</script>

<label for="activity-level">Activity Level
    <select bind:value={activity_level}>
        {#each activity_level_options as option}
            <option value={option}>{option}</option>
        {/each}
    </select>
</label>