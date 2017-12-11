`UserPlayInfo`扩展字段**expand2**

+ goldCoinNumber  -> int    ->(金币数)
+ propsSet  -> Set -> (道具类型集合/数组)
+ propsMap -> Map -> (道具个数)
  + key:String
  + value:Integer
+ giftList -> List<>
  + ​



是否还有可用奖项

List<Integer> enableList = awardRuntimeService.getEnableAwards(activity.getPlatformId(), activity.getId());



