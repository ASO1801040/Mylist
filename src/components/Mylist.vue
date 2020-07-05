<template>
    <div>
        <h1>{{title}}</h1>
        <div>
            
            <input type="text"  v-model="memo" placeholder="memo">
            <button v-on:click="doAction">click</button>
        </div>

    </div>
</template>
<script>
export default {
    name:'HelloList',
    props:{
        title: String,
    },
    data:function(){
        return{
        
        };
    },
    methods:{
        doAction: function(){
            this.$emit('item-event', this.memo);
            
        }
    }

}
</script>