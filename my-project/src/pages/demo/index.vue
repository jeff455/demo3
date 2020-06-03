<template>
    <div>
        <input type="text" v-model="value">
        <button @click="clicks" type="primary">add</button>
        {{value}}

        <ul>
            <li v-for='(item,index) in arr' :key="index">
                {{item}}
            <button size='mini' @click='del(index)'>删除</button>    
            </li>
            
        </ul>

        <button  @bindtap='cli'>按钮</button>
        <button open-type="getUserInfo" @getuserinfo="getuserinfo">按纽纽</button>

        <checkbox-group @change="checkboxChange">
          <label class="weui-cell weui-check__label" v-for="(item,index) in items" :key="index">
            <view class="weui-cell__hd">
              <checkbox :value="item.value" :checked="item.checked"/>
            </view>
            <view class="weui-cell__bd">{{item.name}}</view>
          </label>
        </checkbox-group>

        <Hello msg='hhh' @from='msgs'></Hello>
        {{info}}
    </div>
</template>

<script>
import Hello from '../index/index';
export default {
    data()
    {
        return{
            value:'',
            arr:[1,2,3],
            items: [
                {value: 'USA', name: '美国'},
                {value: 'CHN', name: '中国', checked: 'true'},
                {value: 'BRA', name: '巴西'},
                {value: 'JPN', name: '日本'},
                {value: 'ENG', name: '英国'},
                {value: 'FRA', name: '法国'}
            ],
            info:''
        }
    },
    methods:{
        checkboxChange()
        {

        },
        clicks()
        {
            console.log(this.value);
            this.value='';
        },
        del(index)
        {
            this.arr.splice(index,1);
        },
        cli()
        {
            console.log("taptap");
        },
        msgs(infos){
            // this.info=info;
            console.log(infos);
        }
    },
    components:{
        Hello
    }


}
</script>

<style>

</style>
