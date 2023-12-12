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
        for (let i = 0; i<3; i++) {
            if (boardState[0][i] === "" 
            && boardState[0][i] === boardState[1][i] 
            && boardState[1][i] === boardState[2][i]) {
                return true;
            }
        }
    }

    function markSquare(x: number, y: number){
        if (boardState[y][x] === ""){
            if (counter % 2 === 0){
                boardState[y][x] = "o";
            } else {
                boardState[y][x] = "X";
            }
            checkWin();
            counter+=1
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
    {counter}
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