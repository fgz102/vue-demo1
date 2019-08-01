<template>
    <div>
        <ul>
            <li v-for="(item,index) in lists"
                 :key="index"
                 @click="choose(index)"
                 :class="{active:index==current && current!==''}"
            >{{item}}</li>
        </ul>
        <div><button type="button" @click="add()">添加</button></div>
        <ul>
            <li v-for="(tag,i) in targets" :key="i">{{tag}}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "demo1",
        data() {
            return {
                lists:[1,2,3,4,5,6,7,8,9],
                current:"",
                targets:[]
            }
        },
        methods:{
            choose(index){
                this.current = index;
            },
            add(){
                if(this.current===''){return}
                this.targets.push(this.lists[this.current]);
                this.current = '';
            }
        }

    }
</script>

<style scoped>
li{
    list-style: none;
}
li.active{
    background: green;
}
</style>