<script>
    export let size; // Размер клетки
    export let selectedColor; // Принимаем selectedColor как пропс

    let cellColor = ''; // Цвет клетки

    // Функция для установки выбранного цвета
    function selectColor(color) {
        cellColor = color;
        selectedColor = color;
    }
</script>

<div
        class="cell"
        on:mouseenter={() => { if(selectedColor !== '') cellColor = selectedColor; }}
        style="width: {size}px; height: {size}px; background-color: {cellColor}; position: relative;"
>
</div>

<style>
    .cell {
        border: 1px solid black;
        position: relative;
        cursor: pointer;
    }
</style>
