<script lang="ts" setup>
const links = [
    {
        name: "沐晴夏阳",
        url: "https://www.1987619.com",
    },
    {
        name: "深沟主页",
        url: "https://shyngo.cn/",
    },
    {
        name: "工具箱",
        url: "https://www.gjxx.dev/",
    },
    {
        name: "Mod站",
        url: "https://mod.3dmgame.com/",
    },
    {
        name: "一纸忘忧",
        url: "https://blog.ikxin.com/",
    },
];
</script>
<template>
    <div class="friendly-links">
        <h3>友情链接</h3>
        <div class="links">
            <div class="links-list" v-for="link in links" :key="link.name">
                <a :href="link.url" target="_blank">{{ link.name }}</a>
            </div>
            <div class="links-list apply">
                <a
                    href="https://github.com/3DMXM/www.aoe.top/discussions/1"
                    target="_blank"
                    rel="noopener noreferrer"
                    >申请友链 +
                </a>
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
    margin: 2rem 0;

    h3 {
        font-size: 1.5rem;
        font-weight: 600;
        position: relative;
        padding-bottom: 0.5rem;
        margin-bottom: 0.5rem;

        &::after {
            content: "";
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, #42b883, #47a9bb);
            border-radius: 2px;
        }
    }

    .links {
        display: flex;
        flex-wrap: wrap;
        align-items: center;

        .links-list {
            a {
                display: flex;
                align-items: center;
                justify-content: center;
                padding: 0.5rem;
                border-radius: 8px;
                text-decoration: none;
                font-weight: 500;
                text-align: center;
                transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
                border: 2px solid transparent;
                box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
                word-break: break-word;

                &:hover {
                    transform: translateY(-4px);
                    box-shadow: 0 8px 16px rgba(66, 184, 131, 0.25);
                }
            }

            &.apply {
                a {
                    &:hover {
                        border-color: #47a9bb;
                        box-shadow: 0 8px 16px rgba(71, 169, 187, 0.25);
                    }
                }
            }
        }
    }
}
</style>
