<script lang="ts">
	// Skrypt do strony
    boardState = [['','',''], ['','',''], ['','','']];
</script>

<main>
    <!-- Struktura strony -->
    <table>
        {#each [0,1,2] as i}
            <tr>
                {#each [0,1,2] as j}
                    <td class="cell">
                        ({i}, {j})
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
