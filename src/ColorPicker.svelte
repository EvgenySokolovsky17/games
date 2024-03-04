<!-- ColorPicker.svelte -->
<script>
    let colors = ['red', 'blue', 'green', 'yellow', 'orange']; // Доступные цвета
    let selectedColor = ''; // Выбранный цвет

    // Функция для установки выбранного цвета
    function selectColor(color) {
        selectedColor = color;
    }
</script>

<style>
    .color {
        display: inline-block;
        width: 30px;
        height: 30px;
        margin-right: 5px;
        cursor: pointer;
    }
</style>

<div>
    {#each colors as color}
        <div class="color" style="background-color: {color}" on:click={() => selectColor(color)}></div>
    {/each}
</div>
