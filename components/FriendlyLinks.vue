<script lang="ts" setup>
import { ref } from "vue";

const links = ref<any[]>([]);

async function getLinks() {
    const res = await fetch("https://api.aoe.top/api/friendly/links");
    links.value = await res.json();
}
getLinks();
</script>
<template>
    <div class="friendly-links">
        <h3>友情链接</h3>
        <div class="links">
            <div class="links-list" v-for="link in links" :key="link.name">
                <a :href="link.url" target="_blank">{{ link.name }}</a>
            </div>
        </div>
    </div>
</template>
<script lang="ts">
export default {
    name: "FriendlyLinks",
};
</script>
<style lang="less" scoped>
.friendly-links {
    margin: 1rem 0;

    h3 {
        font-size: 12px;
        font-weight: 600;
        letter-spacing: 0.12em;
        text-transform: uppercase;
        opacity: 0.72;
        margin-bottom: 0.35rem;
    }

    .links {
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        gap: 0.3rem 0.5rem;
        font-size: 12px;

        .links-list {
            a {
                display: flex;
                align-items: center;
                justify-content: center;
                padding: 0.2rem 0.4rem;
                border-radius: 999px;
                text-decoration: none;
                font-weight: 400;
                text-align: center;
                transition:
                    color 0.2s ease,
                    opacity 0.2s ease;
                word-break: break-word;
                color: inherit;
                opacity: 0.72;

                &:hover {
                    opacity: 1;
                }
            }
        }
    }
}
</style>
