<template>
    <div class="streePage">
        <!-- 头部header -->
        <div class="header_box_new">
            <HeaderTop @changeCummuity="changeCummuity" title="晋原街道" />
        </div>
        <div class="content" v-if="isShowContent">
            <StreeComp />
            <StreeFloat :community="community" />
        </div>
    </div>
</template>
<script>
import HeaderTop from '../components/HeaderTop'
import StreeComp from '../streeComp/MapComp'
import StreeFloat from '../streeComp/StreeFloat'
export default {
    components:{
        HeaderTop,
        StreeComp,
        StreeFloat
    },
    data(){
        return{
            isShowContent: false,
            community: '香槟国际'
        }
    },
    mounted(){
        this.isShowContent = true
    },
    methods:{
        // 切换小区
        changeCummuity(com){
            this.community = com;
        },
    }
}
</script>
<style lang="less" scoped>
.streePage{
    width: 100%;
    height: 100%;
    position: relative;
    box-sizing: border-box;
    .header_box_new{
        width: 100%;
        height: 70px;
         box-sizing: border-box;
    }
    .content{
        width: 100%;
        height: calc(100% - 70px);
        position: relative;
         box-sizing: border-box;

    }
}
</style>