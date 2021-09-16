## 六连压五连

>   顺子,连对,三连飞机,四连飞机没有判断length

<img src=".\image\JS\1.png" align="left">



## win32上可以进房,手机上进不去

>   有可能是场景的json文件出现了大小写错误

<img src=".\image\JS\2.png" align="left">



## 通山打供四人玩法，普通房间只给前两位玩家发送牌，后两位玩家没有牌

>   数据库里config_games表的playernum选项配置错误，只有四人玩家，配置成2/3/4导致的



## 记牌器热更以后，点击记牌器按钮，面板无法弹出

>   原因：记牌器的单利对象写在了common里面，但是面板资源加载到了游戏场景里，导致热更游戏出现面板对象野指针
>   解决办法：把记牌器的单利对象写在游戏场景里，面板也加载到游戏场景 或者 把记牌器的单利对象写在common里面，面板加载到MainScene里面

<img src=".\image\JS\3.png" align="left">
