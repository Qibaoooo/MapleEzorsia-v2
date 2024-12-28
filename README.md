# MapleEzorsia v2 (HD client patch for v83)
#### Please follow [setup instructions here](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide) for optimal setup, [gameplay after optimal setup](https://www.youtube.com/watch?v=HxGKn0EjPC0). see the [change log to make sure you're up to date](https://github.com/444Ro666/MapleEzorsia-v2/wiki/Change-Log).     Is your game not working? [Go to Troubleshooting Section](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide#troubleshooting) of the setup guide and see if any fixes help  

#### 2023/10/17 - Major update to how the patch loads wz data, YOU NEED THE [NEW WZ FILE](https://www.mediafire.com/file/6bimll8wtpbclmx/EzorsiaV2_UI.wz/file) OR YOUR GAME WILL CRASH (replace old one, works for all res). [setup for more detailed instructions](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide). For how to toggle off some Ezorsia V2 wz edits see [Troubleshooting Section](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide#troubleshooting)

##### NOTE:     so i've notice some ppl dunno what this is. to clarify: this is a cr@ck that turns the default .exe (from NXXXON) into a HD client/localhost useable for singleplayer or with any server.
##### it still works for it's original design of turning any previously released localhost into HD as well, and also has a few other configurable capabilities specified by the user
##### it doesn't need an injector or other extra .exe file to work because MapleStory already loads up dinput8.dll automatically. just needs the dll to be in the same folder. i did this purposely because so many .exe files in the hacking scene are viruses that make you mine coin
##### first to be released, one of a kind, and truly unique in this scene(or any hacking scene): a cr@ck that is open source, with zero strings attached, designed to be the safest, most transparent setup any end user can get

#### 2023/11/17 - if you used this before this date, `ijl15.dll` is no longer supported, instead re-follow the instructions and put `dinput8.dll` in the folder, delete `ijl15.dll`, and rename `2ijl15.dll`(the original) back to `ijl15.dll`

#### 2023/10/23 - if you used this before this date, nmconew.dll is no longer supported, instead re-follow the instructions and name `ijl15.dll` to `2ijl15.dll`, place new `ijl15.dll` in the folder, delete old nmconew.dll, and rename nmconew2.dll back to nmconew.dll

This DLL modifies addresses in a v83 MapleStory client to change the game window and canvas resolution.  
The goal of this DLL patch is to allow an old 4:3 aspect ratio game to work on 16:9 aspect ratio modern monitors while perserving the original gameplay experience as much as possible. However i also do believe that it is the individual player's choice on how they wish to play the game so i am willing to be flexible regarding optional functionality.
This DLL patch is designed to provide a quality, relatively safe, open source client setup to work alongside open source servers. I do not have the skill or resources available to make a fully working custom client from scratch so this is the best i can do
This DLL also requires some minor modifications to UI.wz to work optimally because i'm currently not skilled enough to change the game in those areas using only DLL, these are also provided in the setup.  
- Coming from another version and need a good localhost? [check out hendi's releases](https://forum.ragezone.com/threads/localhost-workshop.1202021/)

## 使用方法
The default `config.ini` file is included. put it in your game folder (where the .dll is) and the program will try to use it. try to avoid extending the comments (behind ;comment) inside of it or INIReader will be unable to read from it and cause the patch to default to default values for all of the toggle-able values

已测试的开发工具 VS 2019，SDK 10，工具集 VS2019（v142）
2. insert [this ijl15.dll from here](https://github.com/444Ro666/MapleEzorsia-v2/releases) in that directory
2. Run your Game and see how it looks. if you are satisfied then play!
3. insert 'config.ini' in that same directory and check to make the values are as they should be
     - EzorsiaV2WzIncluded=false if you aren't using the UI.wz from the [setup guide](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide) or if your UI.wz doesn't contain MapleEzorsiaV2wzfiles.img
3. Run your Game and enjoy!
          - also CustomLoginFrame=false if there are no login frame modifications at all (note: MapleEzorsiaV2wzfiles.img counts as a modification even if it doesn't directly touch the original login frame, so CustomLoginFrame=true if EzorsiaV2WzIncluded=true)  
               - for compatibility with your own wz edits see the [troubleshooting section](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide#troubleshooting)
4. Run your client!

使用vs打开的时候注意，要使用 Release x86 的模式生成解决方案
- the first publically released standalone dll client for v83 (functionality added on 11/16/2023)
- no WZ/IMG conflicts; Ezorsia V2 will generate its only WZ/IMG file, compatible with any set of WZ or IMG files, provided it is configured correctly!
- the ability to load 3 custom third party dll that you can specify in the config, these must be in the game folder; Ezorsia v2's edits will take precedence over conflicting edits (sometimes a good thing if those dll files have things that prevent the game running, and Ezorsia v2 overwrites those same things)

生成后可在 out/Release 目录下找到 ijl15.dll

先把客户端原本的ijl15.dll重命名成2ijl15.dll，然后把生成的ijl15.dll拷贝到客户端目录下，然后把项目根目录下的config.ini同样复制到客户端目录下，具体配置都在config.ini中
- too many changes to count, see [change log](https://github.com/444Ro666/MapleEzorsia-v2/wiki/Change-Log) and source xD

## 推荐服务端
北斗 https://github.com/SleepNap/BeiDou

## 更新记录

相比主分支 v1

- 支持中文输入/角色中文名(修复卡门问题)
i'd like to thank the members of the [maple dev community](https://discord.gg/DU8j6xrW) who took the time to help me when they did. I'd also like to thank the creator of the [original ezorsia](https://github.com/izarooni/MapleEzorsia) for creating the base i used to work off of and learn from. A special mention to the creators of [MapleClientEditTemplate](https://github.com/MapleStory-Archive/MapleClientEditTemplate) whose re-written utility functions and type definitions helped transition this project towards more advanced client modifications. Finally, I'd like to thank the people who provided the releases and resources in the [setup and development](https://github.com/444Ro666/MapleEzorsia-v2/wiki/v83%E2%80%90Client%E2%80%90Setup%E2%80%90and%E2%80%90Development%E2%80%90Guide) page; i would not have been able to do this work without the work that which was done before me.
- 修复ToolTip超出游戏窗口的问题
- 支持长键盘快捷键
- 交易中心居中
- 增加中文汉化
- 增加魔攻/魔防/命中/回避/跳跃 上限突破
- 增加BossHp百分比显示（在Boss血条的头像下方）
- 免密模式（须服务端支持，客户端仅解除密码限制）
- 调整聊天框文字位置

针对中文环境的一些调整：

1. 装备tooltip字体大小
2. 道具有效期字体大小
3. 修复有效期日期顺序
4. 聊天栏的选项汉化了远征队
5. 在不修改wz的情况下解决了Eqp，Etc汉化后游戏崩溃的问题，Use汉化后吃药没声音的问题