活动中保存在缓存中可变的数据

+ 砍价金额范围
+ 砍价成功概率
+ 限购数量
+ 库存




支付回调相关的类`ActivityToolsPayCallbackServiceImpl`

----

疯狂砍价活动`UserPlayInfo`扩展字段添加的道具剩余信息字段：



```json
{
  "propsMap"：{
  	"index0":{"id":0,"count":0},//道具剩余数
	"index8":{"id":8,"count":0},
	"index2":{"id":2,"count":0}
	...
  },
  "propsTotal":0 //道具总数
}
```





**修改部分**：

+ `/mobile/participation/grouponbargain/queryAwardDetail`接口
  + 砍价内容由一部分变为两部分，出计算助力砍价外还要计算道具砍价值
  + 后端返回一个key为`propBargainRecord`的Map集合，Map中每个Entity表示一个道具砍价记录



+ `/mobile/participation/grouponbargain/bargainByProps`接口
  + 新增的接口，主要供使用道具砍价时调用
  + 该接口前端需要提交的参数：
    + `activityid` → 活动ID
    + `awardId` → 奖项ID
    + `propsId` → 道具ID
    + `relationId` → 关系ID
  + 返回结果：

|         字段         |      含义      |             描述             |
| :----------------: | :----------: | :------------------------: |
|     `propsId`      |   本次使用道具ID   |                            |
|    `propsCount`    | 本次使用道具ID的剩余量 |                            |
|  `relationStatus`  |     关系状态     |     0(进行中)、1(失败)、2(成功)     |
| `bargainValueList` |  道具砍价每刀砍的值   | 如1个道具可以砍3次，则返回的值为{10,20,5} |
|    `propsTotal`    |   全部道具剩余数    |                            |



-----

