# Discord Gemini聊天机器人[简体中文版]
繁体原作者 : [nelsonGX](https://github.com/nelsonGX/discord-gemini-ai)
简体翻译 : [George-Wong1730](https://github.com/George-Wong1730/discord-gemini-ai-ZH_CN/)

## 安裝教学
1. 安裝[Python](https://www.python.org/downloads/release/python-3121/)
2. [安裝PIP](https://bootstrap.pypa.io/get-pip.py)(如果确认有安裝可以跳過)
3. 开启命令行 输入
```
pip install -r requirements.txt
```
4. 设置[config.json](#configjson設置教學)
5. 启动~~原神~~bot.py

## config.json设置教学

* `token`: 你机器人的token，可以前往[Discord Developer Portal](https://discord.com/developers/applications)创建
* `gemini_key`: Gemini的API Key，可以前往[这里](https://makersuite.google.com/u/0/app/apikey)创建
  * 如果有需要更多使用额度(1个API Key一分钟只能用60次)可以使用更多API Key，详细请看[使用多个API Key](#使用多個api-key)
* `developer`: 这应该不用解释吧，写上你的名称就对了
  * 如果[修改提示词](#修改提示词)，这基本可以当成装饰
* `prefix`: 你机器人的前缀，设定成!，幫助指令就是!help
* `bot_name`: 这应该不用解释吧，写上你机器人的名称就对了
   * 如果[修改提示词](#修改提示词)，这还是有一点用
 

## 使用多个API Key
1. 先前往[Google Cloud Console](https://console.cloud.google.com)创建一个专案
2. 進入专案，打开`其他產品`，`API 与服务`
3. 按下`启用 API 和服务`
<br>还未进行翻译
4. 輸入`generative language api`，第一個就是
5. 點進去，然後點`啟用`
6. 你會跑到`API/服務詳細資料`，選到`API 和服務`裡的`憑證`
7. 按下`建立憑證`然後選取`API 金鑰`
8. 他會跳出一個`建立的 API 金鑰`，複製起來
9. 回到`config.json`，設置`gemini_key`成`["API_Key_1","API_Key_2"]` 你要放多少個都可以
10. 恭喜你完成了

## 修改提示詞
1. 先去[這裡](https://makersuite.google.com/u/0/app/prompts/new_chat)，創建一個模板
  * 修改的地方在`Write your prompt example`
2. 按下`Get Code`，選擇`Python`(如果要選的話)
3. 找到`convo = model.start_chat(history=[...])`，複製裡面的`history=[...]`，注意最後不要複製到`)`
4. 打開`bot.py` 找到`async def history(cid):`然後刪掉後面的`history =[...]`，刪到`]`
5. 貼上你剛剛複製的那一大段，完成

