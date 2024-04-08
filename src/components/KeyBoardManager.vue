<script setup>
import "ninja-keys";

const placeholder = 'Buscar Comando'

const hotkeys = [
    {
        id: "Print",
        title: "🖨️ Imprimir",
        hotkey: "ctrl+p",
        section: "Acciones",
        handler: () => {
            window.print()
        },
    },
]

</script>

<template>

    <section>
        <footer class="no-print">pulsa <kbd>Ctrl</kbd> + <kbd>K</kbd> para abrir la paleta de comandos</footer>
        <ninja-keys :hideBreadcrumbs="true" :placeholder="placeholder" :data="hotkeys"></ninja-keys>
    </section>

</template>


<style scoped>
@media print {
    ninja-keys {
        display: none !important;
    }
}

footer {
    background: #fdfdfdfd;
    border-top: 1px solid #eee;
    position: fixed;
    bottom: 0px;
    width: 100%;
    padding: 8px 16px;
    text-align: center;

}
</style>