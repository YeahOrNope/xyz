<script lang="ts">
    // Skrypt do strony
    const boardState = [
        ['', '', ''], 
        ['', '', ''], 
        ['', '', '']
    ];

    let turn = "O";

    function markSquare(x: number, y: number) {
        boardState[y][x] = turn;
        if (turn === "O") {
            turn = "X";
        } else {
            turn = "O";
        }
    }
</script>

<main>
    <!-- Struktura strony -->
    <table>
        {#each [0, 1, 2] as y}
            <tr>
                {#each [0, 1, 2] as x}
                    <td class="cell" on:click={() => {markSquare(x, y)}}>
                        <!-- {boardState[y][x]} -->
                        ({x}, {y})
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