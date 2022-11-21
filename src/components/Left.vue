<template>
    <div class="left">
        <h3>Left组件 --- count is: {{ count }}</h3>
        <button @click="count++">+1</button> &nbsp;&nbsp;
        <button @click="reset_count">重置</button>

        <hr />
        <input ref="mine_input_ref" type="text" v-if="input_show" @blur="show_button" />
        <button @click="show_input" v-else>展示输入框</button>
    </div>
</template>

<script>

export default {

    data() {
        return {
            count: 0,
            input_show: false
        }
    },

    methods: {
        reset_count: function () {
            this.count = 0;
        },

        show_button: function () {
            this.input_show = false;
        },

        show_input: function () {
            this.input_show = true;
            
            // console.log(this.$refs.mine_input_ref);

            this.$nextTick(function() {
                this.$refs.mine_input_ref.focus();
            });
        }
    },

    mounted() {

    }

}

</script>

<style lang="less" scoped>
.left {
    float: left;
    background-color: aqua;
    padding: 5px 0px 20px 20px;
    font-weight: bolder;
    width: 48%;
}

/deep/ h5 {
    color: red;
}
</style>