<script lang="ts">
	// Skrypt do strony
</script>

<main>
    <!-- Struktura strony -->
    <table>
        <tr>
            {#each [0,1,2] as i}
            <td class="cell">
                O
            </td>
        </tr>
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
