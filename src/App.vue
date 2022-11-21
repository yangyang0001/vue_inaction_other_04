<template>
    <div class="root">
        <h1 ref="mine_h1_ref">App根组件</h1>
        <p>
            <button @click="change_color">修改根组件颜色为红色</button>
            &nbsp;&nbsp;
            <button @click="reset_left_count">重置Left.vue中的count值</button>
        </p>
        <Left ref="mine_left_ref"></Left>
        
    </div>
</template>

<script>
import Left from "@/components/Left.vue";
import Right from "@/components/Right.vue";

export default {
    
    components: {
        Left,
        Right
    },

    data() {
        return {
            
        };
    },

    mounted() {
        
    },

    methods: {
        change_color: function() {
            this.$refs.mine_h1_ref.style.color = 'red';
        },

        reset_left_count: function() {
            // console.log(this.$refs.mine_left_ref);
            this.$refs.mine_left_ref.reset_count();
        }
    },
};
</script>

<style lang="less" scoped>
.root {
    padding: 5px 20px 260px 20px;
    background-color: #b9bdb0;
}
</style>