`UserPlayInfo`扩展字段**expand2**

+ `currentGoldCoinNumber`  → int    → (金币数)

+ `firstSignin`    →  boolean    →  (签到标志位)

+ `propsMap`   →  `Map<String,Integer>`  →  (道具信息)

  + **key**  →  道具ID

  + **value**   →  道具数量

  + | 道具ID |  描述  | 道具数量 |
    | :--: | :--: | :--: |
    |  1   | 摇动道具 |  0   |
    |  2   | 伸长道具 |  0   |
    |      |      |      |



+ `gifts`   →  `Map<String,Map<String,Object>>` (桌面奖品信息)

  + `Map<String,Object>`

    + |         key         | value |     描述     |
      | :-----------------: | :---: | :--------: |
      |       awardId       |  int  |    奖项id    |
      |      position       |  int  |    奖品位置    |
      |  needGoldCoinCount  |  int  | 获取奖品需要的金币数 |
      | hadPayGoldCoinCount |  int  | 为奖品已花费的金币数 |
      |                     |       |            |




```json
 {
   "currentGoldCoinNumber": 100,  //用户
        "signinCoin": 0,
   		"totalSigninCoin": 100,
        "propsMap": {
            "1": 1,
            "2": 0
        },
        "gifts": {
            "award_0": {
                "awardId": 65506,
                "needGoldCoinCount": 1000,
                "hadPayGoldCoinCount": 100
            }
        },
   		"security":{
  			"isInBlackList":false,
          	"time":"2017-12-22",
          	"dateDropCoinTotal":10,
          	"dateRecycleCoinTotal":2
          	
		},
   		"ruleRuntimeInfo":{
          	"requestTimeTotal":9,
  			"rule0":{"exceptionTime":1},
          	"rule1":{"exceptionTime":0},
            "rule2":{"exceptionTime":0},
            "rule3":{"exceptionTime":0}
		}
}
```

|          key           |     value     |        含义        |
| :--------------------: | :-----------: | :--------------: |
|    `isInBlackList`     | true \| false |      是否被拉黑       |
|         `time`         |     Date      | 被拉黑的日期，**前端不可见** |
|  `dateDropCoinTotal`   |      int      |    每日累加掉落的金币数    |
| `dateRecycleCoinTotal` |      int      | 每日金币掉落后返还给用户的累加值 |



**备注** ：

`dateDropCoinTotal` 和 `dateRecycleCoinTotal`

+ 发生一次异常时清零
+ 每次首次登录清零