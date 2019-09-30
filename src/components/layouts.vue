<template>
    <section class="container">
        <section class="menu">
            <menus></menus>
        </section>

        <section class="content-container">
            <todo></todo>
        </section>
    </section>
</template>

<script>
import menus from './menus'
import todo from './todo'
export default {
  components: {
    menus,
    todo
  }
}
</script>

<style>
body {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: auto;
    height: auto;
    background-color: #315481;
    background-image: linear-gradient(to bottom, #315481, #918e82 100%);
    background-repeat: no-repeat;
    background-attachment: fixed;
}

.container {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    height: auto;
    width: auto;
    margin: 0;
    overflow: hidden;
}

@media screen and (min-width: 60em) {
    .container {
        left: 5%;
        right: 5%;
    }
}

@media screen and (min-width:  80em) {
    .container {
        left: 10%;
        right: 10%;
    }
}

.menu {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 270px;
    height: auto;
    background-color: #315481;
    background-image: linear-gradient(to bottom, #315481, #918e82 100%);
    background-repeat: no-repeat;
    background-attachment: fixed;
}

.content-container {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 270px;
    transition: all 200ms ease-out;
    transform: translate3d(0, 0, 0);
    background: #d2edf4;
    opacity: 1;
}

</style>
