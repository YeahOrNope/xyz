<script lang="ts">
    // Skrypt do strony
    const boardState = [
        ['', '', ''], 
        ['', '', ''], 
        ['', '', '']
    ];

    let counter = 0
    let gameState = "";

    function checkWin() {
        for (let i = 0; i < 3; i += 1) {
            if (boardState[0][i] !== "" &&
            boardState[0][i] === boardState[1][i] &&
            boardState[1][i] === boardState[2][i]) {
                return true;
            }

            if (boardState[i][0] !== "" &&
            boardState[i][0] === boardState[i][1] &&
            boardState[i][1] === boardState[i][2]) {
                return true;
            }
        }

        if (boardState[0][0] !== "" &&
        boardState[0][0] === boardState[1][1] &&
        boardState[1][1] === boardState[2][2]) {
            return true;
        }

        if (boardState[0][2] !== "" &&
        boardState[0][2] === boardState[1][1] &&
        boardState[1][1] === boardState[2][0]) {
            return true;
        }
        return false;
    }

    function markSquare(x: number, y: number){
        if (boardState[y][x] === ""){
            if (counter % 2 === 0){
                boardState[y][x] = "O";
            } else {
                boardState[y][x] = "X";
            }
        const isWin = checkWin();
        if (isWin){
            if counter % 2 === 0){
                gameState = "O";
            } else {
                gameState = "X";
            }
            counter+=1

            if 
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
                        {boardState[y][x]}
                        <!-- ({x}, {y}) -->
                    </td>
                {/each}
            </tr>
        {/each}
    </table>
    {#if gameSate === "O"}
        O wins
    {/if}
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