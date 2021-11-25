# testApi

下面列出的接口基本都是可以直接使用的，如有问题记得告诉我哦

<!-- TOC -->

- [testApi](#testapi)
    - [支持的请求方法](#支持的请求方法)
    - [通用返回状态说明](#通用返回状态说明)
    - [笑话](#笑话)
        - [获取一条随机笑话](#获取一条随机笑话)
        - [获取多条随机笑话](#获取多条随机笑话)
    - [用户](#用户)
        - [用户验证](#用户验证)
        - [用户注册](#用户注册)
        - [用户注册-json格式数据提交](#用户注册-json格式数据提交)
    - [英雄](#英雄)
        - [英雄外号查询](#英雄外号查询)
        - [英雄简略信息查询](#英雄简略信息查询)
        - [英雄详情查询](#英雄详情查询)
    - [克鲁塞德战纪](#克鲁塞德战纪)
        - [角色查询](#角色查询)
        - [角色查询带分页](#角色查询带分页)
        - [根据类型查询角色](#根据类型查询角色)
        - [角色技能动态图查询](#角色技能动态图查询)
        - [角色新增](#角色新增)
    - [lol-查询](#lol-查询)
    - [lol-详情](#lol-详情)
    - [ninja](#忍者-列表)
    - [随机背景大图](#随机背景大图)
    - [获取 json 格式的天气](#获取-json-格式的天气)
    - [获取 xml 格式菜单](#获取-xml-格式菜单)
    - [聊天机器人](#聊天机器人聊天)
    - [聊天机器人文字转语音](#聊天机器人文字转语音)
    - [新闻列表](#新闻列表)


## 支持的请求方法

- GET（SELECT）：从服务器取出资源（一项或多项）。
- POST（CREATE）：在服务器新建一个资源。
- PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。
- PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。
- DELETE（DELETE）：从服务器删除资源。
- HEAD：获取资源的元数据。
- OPTIONS：获取信息，关于资源的哪些属性是客户端可以改变的。

## 通用返回状态说明

| _状态码_ | _含义_                | _说明_                                              |
| -------- | --------------------- | --------------------------------------------------- |
| 200      | OK                    | 请求成功                                            |
| 201      | CREATED               | 创建成功                                            |
| 204      | DELETED               | 删除成功                                            |
| 400      | BAD REQUEST           | 请求的地址不存在或者包含不支持的参数                |
| 401      | UNAUTHORIZED          | 未授权                                              |
| 403      | FORBIDDEN             | 被禁止访问                                          |
| 404      | NOT FOUND             | 请求的资源不存在                                    |
| 422      | Unprocesable entity   | [POST/PUT/PATCH] 当创建一个对象时，发生一个验证错误 |
| 500      | INTERNAL SERVER ERROR | 内部错误                                            |

## 笑话

### 获取一条随机笑话

> 随机获取笑话的接口

- 请求地址：http://ajax.zllhyy.cn/joke
- 请求方法：get
- 请求参数：无
- 响应内容：随机笑话

### 获取多条随机笑话

> 随机获取笑话的接口

- 请求地址：http://ajax.zllhyy.cn/joke/list
- 请求方法：get
- 请求参数：num

  | 参数名 | 参数说明 | 备注                  |
  | :----- | :------- | :-------------------- |
  | num    | 笑话条数 | 类型为数字,不要给错了 |
- 响应内容：JSON

```json
{
  "msg": "获取10条笑话",
  "jokes": [
    "为什么古装剧里总是有女人会对恩人说：小女子无以为报，唯有以身相许，古代真的存在这种现象吗？ 扯淡，那是因为她喜欢他，要是不喜欢，她就会说：小女子无以为报，唯有来生再报了。",
    "刚才玩了一把狼人杀，网杀。 我是最后一头狼了，悍跳预言家。 游戏已经进行到了三对一，而我主导着好人阵营的风向，本来都已经说好了共同出4。然后我随便刀死一个获得胜利，美滋滋。 结果，在我的发言阶段……正在尽力表演的时候…… 我的舍友突然在旁边大喊了一声…… 卧槽，你居然是狼人！",
    "昨天从外地回来，没回家，今天到家看到老爸醉熏熏地在沙发上。老爸：“什么时候回来的？”我：“昨晚回来的”。他大怒道：“坐碗回来的？怎么不坐盆回来？”我。。。",
    "路上看到一个黑色塑料袋踢了一脚特么是一条睡着的大黑狗，涕泗横流的被追了三里地。",
    "一个胆小紧张的证人正在接受律师的询问。 律师厉声问道：“你是否结过婚？” “是的，我结过一次。”证人声音很小，还有些颤抖。 “那么你和谁结婚了？” “一个女人。” 律师有些发怒，“废话，你当然是和一个女人结婚了。你听说过有谁会和一个男人结婚吗？” 证人颤抖着说：“听说过，我姐姐”。",
    "一位女明星走进鞋店，试了好几双鞋子都不合脚，老板亲自蹲下来替她量脚的尺寸。这位女明星有些近视，看见老板的秃头，以为是自己的膝盖露出来了，便用裙子将它盖住，然而，她立即听到老板的一声闷叫：“真混蛋，又停电了。”",
    "重庆江北北宾路，一酒驾司机被交警拦下.就在他下车一瞬间，这哥们抄起瓶五粮液，一扬脖就喝了半瓶.然后边喝边说，“我不是酒后驾车，我是驾后喝酒.现在我喝了酒，不能开车了，不然要拘6个月.我车就停这，乱停车你们开罚单，拖走也行.我打车走了，明再来提车”.交警茫然...",
    "昨晚喝多了，老婆不在家，让女儿给我倒杯糖水解酒。女儿问：“什么糖都行吗？”我说行。几分钟后，只见女儿颤巍巍的端来一杯水，上面飘着几块口香糖。",
    "昨天发现楼下小摊有5块钱一个的高仿iPhone7模型，于是买了一个然后在一个人多的广场河边假装打电话:“妈蛋，给劳资滚，劳资不会原谅你的，分手吧”然后潇洒的把手机模型扔到了河里，拿出一根烟，故作忧郁的在那里摆了个销魂的姿势站着，看着旁边好多妹子用那花痴的表情看着我。正在我为今天晚上是双飞还是群P伤透脑筋的时候，一个小盆友过来拍了拍我，大声的对我说:“叔叔，你的手机浮上来了。。。最讨厌小盆友了",
    "晚上打的，我：“师傅，服务卡上是你吗？” 他：“是的。” 我：“我看你开车技术很好啊？” 他：“还行吧。” 我：“看你这水平，你以前开过赛车吧？” 他不自信的装B道：“是呀，是呀！这你都能看得出来。” 我：“那是，喜欢兜圈子是不是开赛车留下的职业病？” 他。。。"
  ]
}
```

## 用户

### 用户验证

> 验证用户名是否可用

- 请求地址：http://ajax.zllhyy.cn/user/check
- 请求方法：post
- 请求参数：username

| 参数名   | 参数说明 | 备注                                          |
| :------- | :------- | :-------------------------------------------- |
| username | 用户名   | 不能为空,通过 send 方法传递，格式为 key=value |

```js
xhr.send('username=xxx')
```

- 响应内容：该用户名是否可用

### 用户注册

> 注册用户

- 请求地址：http://ajax.zllhyy.cn/user/register
- 请求方法：post
- 请求参数：username

| 参数名   | 参数说明 | 备注                                          |
| :------- | :------- | :-------------------------------------------- |
| username | 用户名   | 不能为空,通过 send 方法传递，格式为 key=value |

```js
xhr.send('username=xxx')
```

- 响应内容：注册成功或失败

### 用户注册-json格式数据提交

> 注册用户,可以用来测试axios

- 请求地址：http://ajax.zllhyy.cn/user/reg
- 请求方法：post
- 请求参数：username

| 参数名   | 参数说明 | 备注     |
| :------- | :------- | :------- |
| username | 用户名   | 不能为空 |

- 响应内容：注册成功或失败

## 英雄

### 英雄外号查询

> 根据英雄 姓名 查询英雄的 外号

- 请求地址：http://ajax.zllhyy.cn/hero/simple
  - 示例：http://ajax.zllhyy.cn/hero/simple?name=提莫
- 请求方法：get
- 请求参数：name

| 参数名 | 参数说明 | 备注                                    |
| :----- | :------- | :-------------------------------------- |
| name   | 英雄名   | 不能为空,直接跟在 url 后，格式 name=xxx |

- 响应内容：英雄的外号

### 英雄简略信息查询

> 根据英雄 姓名 查询英雄的简略信息

- 请求地址：http://ajax.zllhyy.cn/hero/info
  - 示例：http://ajax.zllhyy.cn/hero/info?name=提莫
- 请求方法：get
- 请求参数：name

| 参数名 | 参数说明 | 备注                                    |
| :----- | :------- | :-------------------------------------- |
| name   | 英雄名   | 不能为空,直接跟在 url 后，格式 name=xxx |

- 响应内容：英雄的简略信息

```json
{
  "title": "迅捷斥候",
  "name": "提莫",
  "bg": "http://img1.dwstatic.com/lol/1512/315320556654/1451366974753.jpg",
  "icon": "http://img.dwstatic.com/lol/1310/246295394773/1382341114833.png",
  "story": "Teemo还有个隐藏被动技能，就是长了个全球嘲讽脸。每次团战必然会被敌方坦克和刺客类英雄集火，你的工作就是要用蘑菇风筝每一个攻击你的人，保持活着，有可能的话顺便杀个人。"
}
```

### 英雄详情查询

> 根据英雄 姓名 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/hero/detail
  - 示例：http://ajax.zllhyy.cn/hero/detail?name=提莫
- 请求方法：get
- 请求参数：name

| 参数名 | 参数说明 | 备注                                    |
| :----- | :------- | :-------------------------------------- |
| name   | 英雄名   | 不能为空,直接跟在 url 后，格式 name=xxx |

- 响应内容：英雄的详细信息

```json
{
  "title": "迅捷斥候",
  "name": "提莫",
  "bgs": [
    "http://img1.dwstatic.com/lol/1512/315320556654/1451366974753.jpg",
    "http://img4.dwstatic.com/lol/1512/315320556654/1451366988149.jpg",
    "http://img2.dwstatic.com/lol/1601/317240712104/1453285617943.jpg",
    "http://img3.dwstatic.com/lol/1601/317240712104/1453285624688.jpg",
    "http://img3.dwstatic.com/lol/1601/317240712104/1453285633565.jpg",
    "http://img.dwstatic.com/lol/1601/317240712104/1453285642044.jpg",
    "http://img2.dwstatic.com/lol/1601/317240712104/1453285650321.jpg",
    "http://img5.dwstatic.com/lol/1601/317240712104/1453285656991.jpg",
    "http://img2.dwstatic.com/lol/1601/317240712104/1453285664288.jpg"
  ],
  "tags": ["魔法", "射手"],
  "icons": [
    "http://img.dwstatic.com/lol/1310/246295394773/1382341114833.png",
    "http://img4.dwstatic.com/lol/1512/315320556654/1451366964489.jpg",
    "http://img5.dwstatic.com/lol/1601/317240712104/1453285557655.jpg",
    "http://img2.dwstatic.com/lol/1601/317240712104/1453285565958.jpg",
    "http://img.dwstatic.com/lol/1601/317240712104/1453285572965.jpg",
    "http://img.dwstatic.com/lol/1601/317240712104/1453285579908.jpg",
    "http://img.dwstatic.com/lol/1601/317240712104/1453285586550.jpg",
    "http://img4.dwstatic.com/lol/1601/317240712104/1453285592508.jpg",
    "http://img2.dwstatic.com/lol/1601/317240712104/1453285599012.jpg"
  ],
  "ability": {
    "life": "30",
    "physical": "50",
    "magic": "70",
    "difficulty": "40"
  },
  "story": "Teemo还有个隐藏被动技能，就是长了个全球嘲讽脸。每次团战必然会被敌方坦克和刺客类英雄集火，你的工作就是要用蘑菇风筝每一个攻击你的人，保持活着，有可能的话顺便杀个人。"
}
```

## 克鲁塞德战纪

### 角色查询

> 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/cq
- 请求方法：get
- 请求参数：query

| 参数名 | 参数说明 | 备注                       |
| :----- | :------- | :------------------------- |
| query  | 英雄名   | 可以为空，为空获取所有数据 |

- 响应内容：JSON

```json
{
  "msg": "获取成功",
  "list": [
    {
      "name": "阎罗使者桂香",
      "icon": "http://p0.qhimg.com/dr/72__/t01d483a1c02dff97d3.png",
      "skill": "恶灵退散"
    },
    {
      "name": "自然的纳兹伦",
      "icon": "http://p7.qhimg.com/dr/72__/t01b33aca0e6daa64a4.png",
      "skill": "狩猎律动"
    },
    {
      "name": "黑桃王后爱丽丝",
      "icon": "http://p5.qhimg.com/dr/72__/t0142106a779023b5d6.png",
      "skill": "命运"
    },
    {
      "name": "稀世怪盗路尼昂",
      "icon": "http://p1.qhimg.com/dr/72__/t01dd39d1a917845d58.png",
      "skill": "怪盗出现"
    },
    {
      "name": "丰饶女神德米特尔",
      "icon": "http://p5.qhimg.com/dr/72__/t018014a8cbb95f7aa5.png",
      "skill": "麦田守卫者"
    },
    {
      "name": "魔法傀儡师贝萝特",
      "icon": "http://p4.qhimg.com/dr/72__/t0198b29952d7d17927.png",
      "skill": "傀儡术"
    }
  ]
}
```

### 角色查询带分页

> 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/cq/page
- 请求方法：get
- 请求参数：query,pageNum,pageSize

| 参数名   | 参数说明 | 备注                       |
| :------- | :------- | :------------------------- |
| query    | 英雄名   | 可以为空，为空表示不搜索   |
| pageNum  | 页码     | 必填，数值                 |
| pageSize | 页容量   | 必填，每页多少条数据，数值 |

- 响应内容：JSON

```js
{
    "msg": "获取成功",
    "totalPage": 206,
    "list": [
        {
            "name": "自然的纳兹伦",
            "icon": "http://p7.qhimg.com/dr/72__/t01b33aca0e6daa64a4.png",
        	"skill": "狩猎律动"
        }
    ]
}
```

### 根据类型查询角色

> 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/cq/category
- 请求方法：get
- 请求参数：type

| 参数名 | 参数说明 | 备注                                                  |
| :----- | :------- | :---------------------------------------------------- |
| type   | 英雄类型 | 不能为空，可选值有:剑士，骑士，弓手，猎人，法师，祭司 |

- 响应内容：JSON

```json
{
    "msg": "获取法师英雄数据",
    "code": 200,
    "data": {
        "heros": [
            {
            "heroName": "黑袍魔女桃乐丝",
            "heroIcon": "http://p4.qhimg.com/dr/72__/t015a7af93e23e5c67c.png",
            "skillName": "奥能脉冲",
            "skillIcon": "http://p3.qhimg.com/dr/52__/t01179c3d8588da2733.png",
            "weaponName": "月之女王",
            "weaponIcon": "http://p2.qhimg.com/dr/45__/t01a05a602fe8a972b8.png"
            },
        ]
}
```



### 角色技能动态图查询

> 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/cq/gif
- 请求方法：get
- 请求参数：name

| 参数名 | 参数说明 | 备注     |
| :----- | :------- | :------- |
| name   | 英雄名   | 不能为空 |


- 响应内容：JSON

```json
{
  "data": {
      "skillGif": "http://p7.qhimg.com/dr/340__/t019779314457e6a37d.gif",
      "heroName": "八神庵"
  },
  "msg": "八神庵的技能图片获取成功",
  "code": 200
}
```

### 角色新增

> 查询英雄的 详细信息

- 请求地址：http://ajax.zllhyy.cn/cq/add
- 请求方法：post
- 请求参数：heroName,heroSkill,skillName

| 参数名    | 参数说明 | 备注     |
| :-------- | :------- | :------- |
| heroName  | 英雄名   | 不能为空 |
| heroIcon  | 技能图片 | 不能为空 |
| heroSkill | 技能名   | 不能为空 |

- 响应内容：JSON

```json
{
    "msg": "新增成功",
    "code": 201,
    "info": {
        "heroIcon": "http://ajax.zllhyy.cn/cq/static/5f89c6f2c695d7126d2768bda47fd7e9",
        "heroName": "超级舞王",
        "skillName": "跳舞"
    }
}
```


## lol-查询

> 查询lol英雄列表

- 请求地址：http://ajax.zllhyy.cn/lol/search
- 请求方法：get
- 请求参数：q

| 参数名 | 参数说明 | 备注         |
| :----- | :------- | :----------- |
| q      | 英雄名   | 查询的关键字 |


- 响应内容：JSON

```json
{
    "code": 200,
    "msg": "获取成功",
    "data": [
              {
                "heroId": "1",
                "name": "黑暗之女",
                "alias": "Annie",
                "title": "安妮",
                "roles": ["mage"],
                "isWeekFree": "0",
                "attack": "2",
                "defense": "3",
                "magic": "10",
                "difficulty": "6",
                "selectAudio": "https://game.gtimg.cn/images/lol/act/img/vo/choose/1.ogg",
                "banAudio": "https://game.gtimg.cn/images/lol/act/img/vo/ban/1.ogg",
                "isARAMweekfree": "0",
                "ispermanentweekfree": "0",
                "changeLabel": "无改动",
                "goldPrice": "4800",
                "couponPrice": "2000",
                "camp": "",
                "campId": "",
                "keywords": "安妮,黑暗之女,火女,Annie,anni,heianzhinv,huonv,an,hazn,hn",
                "icon": "http://game.gtimg.cn/images/lol/act/img/champion/Annie.png"
              }
    ]
}
```

## lol-详情

> 查询lol英雄详情

- 请求地址：http://ajax.zllhyy.cn/lol/info
- 请求方法：get
- 请求参数：id

| 参数名 | 参数说明 | 备注   |
| :----- | :------- | :----- |
| id     | 英雄id   | 英雄id |


- 响应内容：JSON

```json
{
    "code": 200,
    "msg": "获取成功",
    "data": {
        "hero":"英雄信息",
        "skins":"皮肤信息",
        "spells":"技能信息"
    }
}
```



## 忍者-列表

返回所有忍者数据

* 请求地址:http://ajax.zllhyy.cn/ninja/search
* 请求方法：get
* 请求参数：无

```json
{
  "code": 200,
  "msg": "获取成功",
  "data": [
    {
      "name": "猿飞日斩",
      "icon": "http:https://game.gtimg.cn/images/hyrz/zlkdatasys/images/image/20180928/ac7b536850e29ae8553f0418fb440904.png",
      "title": "「火影继承人」",
      "class": [
        "boy",
        "a",
        "muye"
      ]
    }
  ]
}

```





## 随机背景大图

返回随机的lol英雄皮肤

* 请求地址:http://ajax.zllhyy.cn/cover/random
* 请求方法：get
* 请求参数：无

```json
{
    "code": 200,
    "msg": "获取成功",
    "url": "http://ossweb-img.qq.com/images/lol/web201310/skin/big90000.jpg"
}
```



## 获取 json 格式的天气

- 请求地址：http://wthrcdn.etouch.cn/weather_mini
  - 示例：http://wthrcdn.etouch.cn/weather_mini?city=深圳
- 请求方法：get
- 请求参数：city

| 参数名 | 参数说明     | 备注               |
| :----- | :----------- | :----------------- |
| City   | 查询的城市名 | 不能为空，不能写错 |

- 响应内容：json

```json
{
  "data": {
    "yesterday": {
      "date": "15日星期三",
      "high": "高温 31℃",
      "fx": "无持续风向",
      "low": "低温 26℃",
      "fl": "<![CDATA[<3级]]>",
      "type": "多云"
    },
    "city": "深圳",
    "forecast": [
      {
        "date": "16日星期四",
        "high": "高温 32℃",
        "fengli": "<![CDATA[<3级]]>",
        "low": "低温 27℃",
        "fengxiang": "无持续风向",
        "type": "阵雨"
      },
      {
        "date": "17日星期五",
        "high": "高温 32℃",
        "fengli": "<![CDATA[<3级]]>",
        "low": "低温 27℃",
        "fengxiang": "无持续风向",
        "type": "雷阵雨"
      },
      {
        "date": "18日星期六",
        "high": "高温 32℃",
        "fengli": "<![CDATA[<3级]]>",
        "low": "低温 27℃",
        "fengxiang": "无持续风向",
        "type": "雷阵雨"
      },
      {
        "date": "19日星期天",
        "high": "高温 32℃",
        "fengli": "<![CDATA[<3级]]>",
        "low": "低温 25℃",
        "fengxiang": "无持续风向",
        "type": "雷阵雨"
      },
      {
        "date": "20日星期一",
        "high": "高温 29℃",
        "fengli": "<![CDATA[<3级]]>",
        "low": "低温 24℃",
        "fengxiang": "无持续风向",
        "type": "阵雨"
      }
    ],
    "ganmao": "各项气象条件适宜，发生感冒机率较低。但请避免长期处于空调房间中，以防感冒。",
    "wendu": "30"
  },
  "status": 1000,
  "desc": "OK"
}
```

## 获取 xml 格式菜单

- 请求地址：http://ajax.zllhyy.cn/food.xml

- 请求方法：get
- 请求参数：无



- 响应内容：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<breakfast_menu>
	<food>
		<name>Belgian Waffles</name>
		<price>$5.95</price>
		<description>Two of our famous Belgian Waffles with plenty of real maple syrup</description>
		<calories>650</calories>
	</food>
	<food>
		<name>Strawberry Belgian Waffles</name>
		<price>$7.95</price>
		<description>Light Belgian waffles covered with strawberries and whipped cream</description>
		<calories>900</calories>
	</food>
	<food>
		<name>Berry-Berry Belgian Waffles</name>
		<price>$8.95</price>
		<description>Light Belgian waffles covered with an assortment of fresh berries and whipped cream</description>
		<calories>900</calories>
	</food>
	<food>
		<name>French Toast</name>
		<price>$4.50</price>
		<description>Thick slices made from our homemade sourdough bread</description>
		<calories>600</calories>
	</food>
	<food>
		<name>Homestyle Breakfast</name>
		<price>$6.95</price>
		<description>Two eggs, bacon or sausage, toast, and our ever-popular hash browns</description>
		<calories>950</calories>
	</food>
</breakfast_menu>

```

## 聊天机器人聊天

- 请求地址：http://www.liulongbin.top:3006/api/robot
- 请求方法：get
- 请求参数：spoken

| 参数名 | 参数说明           | 备注 |
| :----- | :----------------- | :--- |
| spoken | 要跟机器人聊的内容 |      |

- 响应内容：聊天的信息

```json
{
  "data": {
    "type": 5000,
    "info": {
      "text": "*^_^*好好好~"
    }
  },
  "message": "success"
}
```

| 参数名  | 类型   | 说明                                        |
| :------ | :----- | ------------------------------------------- |
| data    | object | 服务器返回的消息对象                        |
| + type  | int    | 获取聊天消息是否成功的状态码，5000 表示成功 |
| + info  | object | 聊天消息对象                                |
| ++ text | string | 机器人返回的聊天内容                        |
| message | string | 请求结果的描述消息                          |

## 聊天机器人文字转语音

- 请求地址：http://www.liulongbin.top:3006/api/synthesize
- 请求方法：get
- 请求参数：key,info

| 参数名 | 参数说明       | 备注 |
| :----- | :------------- | :--- |
| text   | 要转语音的文字 |      |

- 响应内容：语音的url
```json
{
  "status": 200,
  "message": "success",
  "voiceUrl": "https://dds.dui.ai/runtime/v1/synthesize?voiceId=qianranfa&speed=0.8&volume=100&audioType=wav&text=%E4%BD%A0%E5%A5%BD"
}
```



| 参数名   | 类型   | 说明                                      |
| :------- | :----- | ----------------------------------------- |
| status   | int    | 请求是否成功，200：成功，否则失败         |
| message  | string | 请求结果的描述消息                        |
| voiceUrl | string | 语音消息的URL地址，可通过 `` 标签进行播放 |



## 新闻列表

+ 接口URL：  http://www.liulongbin.top:3006/api/news
+ 调用方式： GET
+ 参数格式：无
+ 响应格式：

| 数据名称  | 数据类型 | 说明                                         |
| --------- | -------- | -------------------------------------------- |
| status    | Number   | 200 获取新闻列表成功；500 获取新闻列表失败！ |
| msg       | String   | 对 status 字段的详细说明                     |
| data      | Array    | 新闻列表数组                                 |
| +id       | Number   | 新闻Id                                       |
| +title    | String   | 新闻标题                                     |
| +source   | String   | 新闻来源                                     |
| +cmtcount | Number   | 评论数量                                     |
| +tags     | String   | 标签                                         |
| +img      | String   | 图片地址                                     |
| +time     | String   | 发表时间                                     |

+ 返回示例：

```json
{
    "status": 200,
    "msg": "获取新闻列表成功",
    "data": [
        {
            "id": 1,
            "title": "5G商用在即，三大运营商营收持续下降",
            "source": "新京报经济新闻",
            "cmtcount": 58,
            "tags": "三大运营商,中国移动,5G商用",
            "img": "/images/0.webp",
            "time": "2019-10-28T03:50:28.000Z"
        }
    ]
}
```

