<script lang="ts">
    const gender_options = ["Male", "Female"];
    export let gender:string;
</script>

<label for="gender">Gender
    <select bind:value={gender}>
        {#each gender_options as option}
            <option value={option}>{option}</option>
        {/each}
    </select>
</label>