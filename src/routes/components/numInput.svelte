<script lang="ts">
    export let label:String;
    export let value:Number;
</script>

<label>
    {label}
    <input type="number" bind:value={value} min="10" max="100">
</label>