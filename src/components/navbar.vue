<script>
import { RouterLink } from 'vue-router';

export default{
    data(){
        return{
            routerLinks:[
                {
                    show:'🏠',
                    name:'home'
                },
                {
                    show:'前台',
                    name:'about'
                },{
                    show:'後台',
                    name:'about'
                }
        ]
// 路由陣列 改這邊控制導覽列



        }
    }
}

</script>
<template>
<!-- 牛B  這個寫法可以欸  v-for給to綁定的內還有內文賦值 只要改上面的data就能新增了 -->
<nav >
    <!-- 綁定名字的路由比較好維護 -->
        <RouterLink :to="{name:i.name}" class="links" v-for="(i,index) in routerLinks" :key="index">
            {{ i.show }}
        </RouterLink>
    <!-- <form action="" class="searchAria">
        <label for=""> 搜索→
        <input type="search" placeholder="搜尋" class="search">
        </label>
        <input type="button" name="clickBtn" id="" class="clickBtn"  value="按我搜尋">
    </form> -->
</nav>

</template>

<style lang="scss" scoped>
*{
    font-family: '正黑體';
    transition: 1s;
}

nav{
    display: flex;
    text-decoration: none;
    height: 7vh;
    background-color: rgb(127, 158, 168);
    box-sizing: border-box;
    padding-top: 1vh;
    padding-bottom: 1vh;
    .links{
        margin: 0 30px;
        text-decoration: none;
        font-size: 16pt;
        text-align: start;
        color: #fff;
        border: 2px  #fff;
        border-style: dashed ;
        border-radius: 10px;
        padding: 5px;
        &:hover{
            transform: scale(1.1);
        }
    }
    // .searchAria{
    //     width: 70vw;
    //     label{
    //         font-size: 16pt;
    //         // text-shadow: #fff 1px 1px 1px;
    //         font-weight: 900;
    //         text-shadow:#fff 5px 0 5px,#fff 0 5px  5px,#fff 0 -5px  5px,#fff -5px  0 5px;
    //     }
    //     .search{
    //         width: 60%;
    //         height: 80%;
    //         border: none;
    //         transform:skew(-15deg);
    //         &:focus{
    //             transform: skew(0);
    //         }
    //     }
    //     .clickBtn{
    //         margin: 0 100px;
    //         border: none;
    //         background-color: cadetblue;
    //         border: 2px groove rgb(67, 111, 113);
    //         padding: 5px;
    //         border-radius: 10px 0 10px 0 ;
    //         color: #fff;
    //         font-weight: 700;
    //         &:active{
    //             transition: .5s;
    //             background-color: rgb(67, 111, 113);
    //             color: #fff;
    //             border-color: cadetblue;
    //             transform: scale(.95);
    //         }
    //     }
    // }
}
</style>