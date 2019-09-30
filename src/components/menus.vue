<template>
    <div class="list-todos">
        <a class="list-todo activeListClass list" v-for="item in items" :key="item.id">
            <span class="icon-lock" v-if="item.locked"></span>
            <span class="count-list">{{ item.count }}</span>{{ item.title }}
        </a>
        <a class="link-list-new" > <!--新增菜单-->
            <span class="icon-plus"></span>
            新增
        </a>
    </div>
</template>

<script>
export default {
    data () {
        return {
            items: [
                { title: '星期一', count: 1, locked: true },
                { title: '星期二', count: 2, locked: true },
                { title: '星期三', count: 3, locked: false }
            ]
        }
    }
}
</script>

<style scoped>
@import url("../common/style/icon.css");
.list-todos > a {
    box-shadow: rgba(255,255,255,.15) 0 1px 0 0;
    display: block;
    line-height: 1.5em;
    padding: .75em 2.5em;
    position: relative;
    text-decoration: none;
    text-align: left;
    cursor: pointer;
    overflow-x:hidden;
}

.list-todos > .link-list-new {
    text-align: left;
    color: #d2edf4;
    cursor: pointer;
}

.list-todos > .list-todo {
    color: rgba(255,255,255,.4);
}

.list-todos > .list-todo:hover,
.list-todos > .list-todo:active {
    color:white;

}

.count-list {
    transition: all 200ms ease-in;
    background: rgba(255,255,255,.1);
    border-radius: 1em;
    float: right;
    font-size: .7rem;
    line-height: 1;
    margin-top: .25rem;
    margin-right: -1.5em;
    padding: .3em .5em;
}

.list-todos > .list-todo:hover > .count-list,
.list-todos > .list-todo:active > .count-list {
    background: #2cc5d2;
}

[class^="icon-"],
[class*=" icon-"] {
    float: left;
    margin-left: -1.5rem;
    margin-right: .5rem;
    margin-top: .1rem;
    width: 1em;
}

</style>
