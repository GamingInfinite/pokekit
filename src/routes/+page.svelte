<script lang="ts">
    let playerX = 0,
        playerY = 0;
    let coordinateGrid = [0, 0, 0, 0, 0];

    function randColor(color: string) {
        let r, g, b;
        r = Math.round(Math.random() * 255);
        g = Math.round(Math.random() * 255);
        b = Math.round(Math.random() * 255);
        switch (color) {
            case "r":
                return r;
            case "g":
                return g;
            case "b":
                return b;
            default:
                return { r, g, b };
        }
    }
</script>

<svelte:head>
    <title>TableTalk</title>
</svelte:head>

<div class="flex flex-col">
    <div class="grid grid-rows-{coordinateGrid.length} w-fit">
        {#each coordinateGrid as temp, j}
            <div class="grid grid-cols-{coordinateGrid.length}">
                {#each coordinateGrid as temp, j}
                    <div
                        class="flex flex-nowrap w-8 h-8 justify-center items-center"
                        style="background-color: rgb({randColor("r")}, {randColor("g")}, {randColor("b")});"
                    >
                        A
                    </div>
                {/each}
            </div>
        {/each}
    </div>
</div>
