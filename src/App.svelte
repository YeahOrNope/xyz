<script lang="ts">
    // Skrypt do strony
    const boardState = [
        ['', '', ''], 
        ['', '', ''], 
        ['', '', '']
    ];

    function markSquare() {
        console.log("Clecked");
    }
</script>

<main>
    <!-- Struktura strony -->
    <table>
        {#each [0, 1, 2] as y}
            <tr>
                {#each [0, 1, 2] as x}
                    <td class="cell" on:click={() => {}}>
                        {boardState[y][x]}
                    </td>
                {/each}
            </tr>
        {/each}
    </table>
</main>

<style>
    /* Styl strony */
    .cell {
        width: 100px;
        height: 100px;
        background-color: aqua;
        color: black;
        text-align: center;
        font-size: 40px;
    }
</style>