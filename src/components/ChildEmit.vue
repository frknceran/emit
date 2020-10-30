<template>
    <div class="child-emit">
        <h4>Child with emit</h4>
        <p>Value of hübele Child:</p>
        {{ valueEmit }}
        <br>
        <br>
        Value cat: <input type="text"
            @input="$emit('update-value-by-child', valueEmit)"
            v-model="valueEmit.cat">
        <br>
        Value Dog:<input type="text"
            v-model="valueEmit.dog">
    </div>
</template>

<script>
export default {
    name:"ChildEmit",
    
    props: {
        initialValue: Object
    },

    data() {
        return {
            valueEmit: Object.assign({}, this.initialValue)
        }
    }
}
</script>

<style scoped>
    h1,h2 {
        font-weight: normal;
    }
    ul {
        list-style-type: none;
        padding: 0px; 
    }
    li {
        display: inline-block;
        margin: 0 10px;
    }
    a {
        color: #42b983;
    }
</style>