`UserPlayInfo`扩展字段**expand2**

+ `currentGoldCoinNumber`  → int    → (金币数)

+ `firstSignin`    →  boolean    →  (签到标志位)

+ `propsMap`   →  `Map<String,Map<String, Integer>>`  →  (道具信息)

  + **key**  →  道具ID

  + **value**   →  `Map<String, Integer>`

    + key:String  → 道具名称  
    + value:Integer  → 道具数量

  + |    名称     |  描述  | 初始值  |
    | :-------: | :--: | :--: |
    | shakeTool | 摇动道具 |  0   |
    | pushTool  | 伸长道具 |  0   |
    |           |      |      |



+ `gifts`   →  `Map<String,Map<String,Object>>` (桌面奖品信息)

  + `Map<String,Object>`

    + |         key         | value |     描述     |
      | :-----------------: | :---: | :--------: |
      |       awardId       |  int  |    奖品id    |
      |      position       |  int  |    奖品位置    |
      |  needGoldCoinCount  |  int  | 获取奖品需要的金币数 |
      | hadPayGoldCoinCount |  int  | 为奖品已花费的金币数 |
      |                     |       |            |




