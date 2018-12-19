<template>
    <div class='test-demo'>
        <div class='test' @click='click'>
            <input class='text'>{{text}}</input>
            <input class='text1'>{{text}}</input>
            <input class='text2'>{{text}}</input>
        </div>
        <div class='test2' v-show='showText'>
            <span class='text2'>{{clickCount}}</span>
        </div>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                text: '测试',
                clickCount: 'Quae hic ut ab perferendis sit quod architecto, \
                    dolor debitis quam rem provident aspernatur tempora \
                    expedita.',
                status: true
            }
        },
        computed: {
            showText() {

            }
        }
        mounted() {
            console.log('mounted');
        },
        watch: {

        }
        methods: {
            click() {
                console.log('clickCount:', this.clickCount);
                console.log('status:', !this.status);
            }
        }
    }
</script>

<style scoped>
    .test-demo {
        width: 100%;
        height: 100%;
    }
    .test {
        width: 200px;
        height: 100px;
        background-color: lightblue;
        line-height: 100px;
        cursor: pointer;
        margin: 40px;
    }
    .test2 {
        width: 300px;
        height: 200px;
        line-height: 200px;
        background-color: yellow;
        margin: 40px;
    }
</style>