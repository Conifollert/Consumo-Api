<script>
export default{
    props: ["messages"],
};
</script>

<template>
    <div class="chat-box">
        <div v-for="({input, color, direction, nombre}, i) in messages"
        :key="i"
        :class="{left: direction == 'left', right: direction == 'right'}">

        <span class="nombre">{{ nombre }}</span>
        <p :style="{backgroundColor: color}" class="message">
            <span>{{ input }}</span>
        </p>
        </div>
    </div>
</template>

<style lang="scss">
.chat-box {
    background-color: #eee7dd;
    box-shadow: 0px 0px 4px 1px black;
    overflow-y: scroll;
    max-height: 417px;
    padding: 10px 15px;
    .nombre{
        font-size: 0.7rem;
        color: gray;
    }
    > div{
        display: flex;
        flex-direction: column;
    }
}

.left{
    align-self: flex-start;
    text-align: left;
    align-items: flex-start
}

.right{
    align-self: flex-end;
    text-align: right;
    align-items: flex-end;
}

.message{
    border-radius: 20px;
    padding: 5px 10px;
    margin: 5px 0px;
    width: fit-content;
    i{
        font-style: normal;
        font-size: 0.7rem;
    }
}
</style>