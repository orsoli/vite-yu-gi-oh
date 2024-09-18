<template>
    <div class="container">
        <div class="loader">
        </div>
    </div>
</template>

<style lang="scss" scoped>
/* HTML: <div class="loader"></div> */
.loader {
    width: fit-content;
    font-weight: bold;
    font-family: monospace;
    font-size: 30px;
    clip-path: inset(0 3ch 0 0);
    animation: l4 1s steps(4) infinite;
    position: absolute;
    top: 50%;
    left: 50%;
    translate: -50%, -50%;
}

.loader:before {
    content: "Loading..."
}

@keyframes l4 {
    to {
        clip-path: inset(0 -1ch 0 0)
    }
}
</style>