<template>
    <div class="container">
        <h1>子组件</h1>
        <p>{{ money }}</p>
        <button @click="changeMoney()">花50元</button>
    </div>
</template>
<script>


export default {
    name: 'Son2',
    //子组件接收父组件数据，使用props
    props: {
        money: {
            type: Number,
            default: 0
        }
    },

    // props 父组件数据
    // emit触发自定义事件的函数
    setup(props, { emit }) {
        //获取父组件数据money
        console.log(props.money);

        //向父组件传值
        const changeMoney = () => {
            //消费50元
            //通知父组件，moeny需要改变成50
            emit('change-money', 50)
        }

        return { changeMoney }

    }
}
</script>