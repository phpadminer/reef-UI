<template>
    <div class="reef-group-button">
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "reef-group-button",
        mounted() {
            for(let node of this.$el.children){
                let nodeName = node.nodeName.toLowerCase();
                if(nodeName !== 'button'){
                    console.warn(`reef-group-button的子元素需要的是button,你所给的是${nodeName}`);
                }
            }
        }
    };
</script>

<style scoped lang="scss">
    .reef-group-button {
        display: inline-flex;
        vertical-align: middle;

        > .reef-button {
            border-radius: 0;
            margin-left: -1px;

            &:first-child {
                border-top-left-radius: var(--border-radius);
                border-bottom-left-radius: var(--border-radius);
                margin-left: 0;
            }

            &:last-child {
                border-top-right-radius: var(--border-radius);
                border-bottom-right-radius: var(--border-radius);
            }

            &:hover {
                position: relative;
                z-index: 1;
            }
        }
    }
</style>