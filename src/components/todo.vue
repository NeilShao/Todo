 <template>
    <div class="page lists-show"><!--最外层容器-->
        <nav><!--容器上半部分-->
            <div class="nav-group"> <!--移动端的菜单图标-->
                <a class="nav-item">
                    <span class="icon-list-unordered"></span>
                </a>
            </div>
            <h1 class="title-page">
                <span class="title-wrapper">{{todo.title}}</span> <!-- 标题-->
                <span class="count-list">{{todo.count}}</span><!-- 数目-->
            </h1>
            <div class="nav-group right"><!-- 右边的删除，锁定图标容器-->
                <div class="options-web">
                    <a class="nav-item"> <!-- 锁定图标-->
                        <span class="icon-lock" v-if="todo.locked"></span>
                        <span class="icon-unlock" v-else></span>
                    </a>
                    <a class="nav-item"><!-- 删除图标-->
                        <span class="icon-trash"></span>
                    </a>
                </div>
            </div>

            <div class="form todo-new input-symbol"> <!-- 新增单个代办单项输入框,监听了回车事件，双向绑定text值,监听了disabled属性，在todo.locked为true的情况下无法编辑-->
                <input type="text" v-model="text" placeholder='请输入' @keyup.enter="onAdd" :disabled="todo.locked" />
            <span class="icon-add"></span>
            </div>
        </nav>
        <div class="content-scrollable list-items">
            <!--容器下半部分-->
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            todo: {
                title: '星期一',
                count: 12,
                locked: false
            },

            items: [
                { checked: false, text: '新的一天', isDelete: false },
                { checked: false, text: '新的一天', isDelete: false },
                { checked: false, text: '新的一天', isDelete: false }
            ],

            text: ''
        }
    },

    methods: {
        onAdd () {
            this.items.push({
                checked: false, text: this.text, isDelete: false
            })
            this.text = ''
        }
    }
}
</script>

<style scoped>
.page.lists-show {
    background: white;
    top: 5em !important;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
} 

.lists-show > nav {
    background: linear-gradient(to bottom, #d0edf5, #e1e5f0 100%);
    height: 5em;
    text-align: center;
}

@media screen and (min-width: 40em) {
    .lists-show > nav {
        text-align: left;
    }

    .title-page {
        left: 1rem;
        right: 6rem;
    }
}

.title-page {
    position: absolute;
    top: 0;
    right: 3rem;
    bottom: auto;
    left: 3rem;
    cursor: pointer;
    font-size: 1.125em; 
    white-space: nowrap;
    margin: 10px 0px;
}

.title-wrapper {
    color: #1c3f53;
    display: inline-block;
    padding-right: 1.5rem;
    vertical-align: top;
    max-width: 100%;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

.count-list {
    background: #2cc5d2;
    border-radius: 1em;
    color: white;
    display: inline-block;
    font-size: .7rem;
    line-height: 1;
    margin-left: -1.25rem;
    margin-top: -4px;
    padding: .3em .5em;
    vertical-align: middle;
}

</style>
