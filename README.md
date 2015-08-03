# Logbook
a chrome plugin for kancolle the flash web game

---

Logbook 是一个解析网页游戏 舰队Collection 网络数据以方便玩家了解游戏信息的 Chrome 浏览器插件

要在 Chrome 浏览器上使用 Logbook :

1. 在浏览器设置(`Settings`)中的扩展程序(`Extensions`)里启用开发者模式(`Developer mode`)
2. 加载未打包的扩展应用(`Load unpacked extension...`)
3. 如果插件是已经打包好的 `.crx` 格式，直接双击安装即可
4. 在浏览器页面右键选择审查元素(`Inspect Element`)
5. 也可以经由浏览器菜单中的 更多工具(`More tools`) 中的 开发者工具(`Developer Tools`) 访问
6. 点击 Logbook 选项卡， Logbook 即可开始工作
7. 为了能使插件正常，你可能需要重新刷新游戏页面

---

**工作原理:**

Chrome 允许开发者工具访问用户与网站之间通信的网络数据  
Logbook 通过分析游戏flash与服务器之间的通信数据，将一些细节提供给玩家参考

插件第一次运行时需要读取一些关键数据(舰船、装备的属性等)，这需要您重新刷新游戏页面  

```js
[安装插件]->[审查元素]->[点击Logbook]->[刷新游戏页面]
```

战斗结果预告功能需要您再启用插件后至少切换一次母港画面，否则将缺少必要数据

由于技术原因，KCLogbook无法在战斗途中启用并分析结果  

这是因为游戏在出击时会收到一条关键数据，该数据包含了出击舰队的信息  
若缺乏该信息，KCLogbook无法正常分析战斗结果

```js
[审查元素]->[点击Logbook]->[打开游戏页面]->[可以正常使用]

[打开游戏页面]->[审查元素]->[Logbook]->[游戏中入渠]->[游戏中进入母港]->[可以正常分析战斗]

[打开游戏页面]->[审查元素]->[Logbook]->[游戏中工厂]->[游戏中进入母港]->[可以正常分析战斗]

[打开游戏页面]->[母港画面]->[审查元素]->[Logbook]->[无法分析战斗]
```

这是因为在游戏在`切换至`母港的时候会收到一条关键数据，该数据包含了当前舰队的信息  
若缺乏该信息，KCLogbook无法正常分析战斗结果

当前插件尚未添加对支援舰队的数据分析，这可能导致战斗结果分析不准确，请以游戏显示为准

---

**声明:**

* Logbook 不会解析除 舰队Collection 游戏以外任何网站的通信数据
* Logbook 不会记录、保存或上传任何有关用户的隐私或账号相关的信息和数据
* Logbook `不会修改`任何网络数据


**Logbook 可能会在使用过程中失效，届时插件可能显示错误数据，请以游戏显示的数据为准**

**由于插件显示错误导致的损失，包括但不限于：大破进击沉船等，开发者恕不承担，请谨慎使用**

**Logbook 绝对不会修改您的网络通信数据，也不会向DMM或第三方服务器发送任何数据**

---

**其他:**

当前版本: 0.9.1  
开发者: MG  
E-mail: kclogbook@163.com  
