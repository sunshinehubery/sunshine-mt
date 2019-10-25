<template>
    <div class="m-menu">
        <!-- 左侧导航栏头 -->
        <dl class="nav" @mouseleave="mouseleave">
            <dt>全部分类</dt>
            <dd v-for="(item, index) in menu" :key="index" @mouseenter="enter">
                <i :class="item.type"/>{{item.name}}<span class="arrow"/>
            </dd>
        </dl>
        <div 
            v-if="kind"
            class="detail"
            @mouseenter="sover"
            @mouseleave="sout">
            <template v-for="(item, index) in curdetail.child">
                <h4 :key="index">{{item.title}}</h4>  
                <span
                    v-for="v in item.child"
                    :key="v">{{ v }}</span>        
            </template>
        </div>
        <!-- 左侧导航栏尾 -->
    </div>
</template>
<<script>
    export default {
        data() {
            return {
                kind: '',  //储存type
                menu: [{
                    type:'food',
                    name:'美食',
                    child:[{
                        title:'美食',
                        child:['代金券','甜点饮品','火锅','自助餐','小吃快餐'],
                    }],
                },{
                    type:'takeout',
                    name:'外卖',
                    child:[{title:'外卖',
                    child:['美团外卖'],
                    }],
                },{
                    type:'hotel',
                    name:'酒店',
                    child:[{
                        title:'酒店星级',
                        child:['经济型','舒适/三星','高档/四星','豪华/五星'],
                    }],
                },{
                    type:'food',
                    name:'美食',
                    child:[{
                        title:'美食',
                        child:['代金券','甜点饮品','火锅','自助餐','小吃快餐'],
                    }],
                },{
                    type:'takeout',
                    name:'外卖',
                    child:[{title:'外卖',
                    child:['美团外卖'],
                    }],
                },{
                    type:'hotel',
                    name:'酒店',
                    child:[{
                        title:'酒店星级',
                        child:['经济型','舒适/三星','高档/四星','豪华/五星'],
                    }],
                }],
            }
        },  
        computed: {
            //获取相应的导航栏中类目中的内容
            curdetail:function(){
                return this.menu.filter((item) => item.type===this.kind)[0];
            }
        },  
        methods: {
            //鼠标移除菜单栏，将kind置空
            mouseleave:function(){
                let self=this;
                self._timer=setTimeout(() => {
                    self.kind='';
                }, 200);
            },
            //鼠标移到某一个类目，将该类中的type赋值给kind
            enter:function(e) {
                this.kind=e.target.querySelector('i').className
                //console.log(e);
            },
            //移到副菜单栏，取消置空kind
            sover:function() {
                clearTimeout(this._timer);
            },
            //移除鼠标置空kind，隐藏副菜单栏
            sout:function(){
                this.kind='';
            }
        },  
    }
</script>