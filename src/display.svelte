<script>
    import Cell from './Cell.svelte';

    let selectedColor = ''; // Цвет по умолчанию

    const colors = ['red', 'blue', 'green', 'yellow', 'orange']; // Доступные цвета

    // Функция для установки выбранного цвета
    function selectColor(color) {
        selectedColor = color;
    }
</script>

<style>
    .grid {
        display: grid;
        grid-template-columns: repeat(10, 1fr); /* 10 столбцов */
        grid-template-rows: repeat(10, 1fr); /* 10 строк */
        gap: 0;
        padding: 302px;
        margin: 302px;
        column-gap: none; /* Устанавливаем отступы между столбцами */
        row-gap: none; /* Устанавливаем отступы между строками в 0 */
    }

    .color-picker {
        position: fixed;
        top: 20px; /* Располагаем палитру вверху страницы */
        left: 50%;
        transform: translateX(-50%);
        display: flex;
    }

    .color {
        width: 20px;
        height: 20px;
        margin-right: 5px;
        cursor: pointer;
    }
</style>

<div class="color-picker">
    {#each colors as color}
        <div
                class="color"
                style="background-color: {color}"
                on:click={() => selectColor(color)}
        ></div>
    {/each}
</div>

<div class="grid">
    {#each Array(10) as _, rowIndex}
        {#each Array(10) as _, colIndex}
            <Cell key={rowIndex * 10 + colIndex} size={20} selectedColor={selectedColor}/>
        {/each}
    {/each}
</div>
