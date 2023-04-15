# AiNiee-chatgpt
基于mtool导出的json文件，chatgpt自动批量翻译工具



——————————————————————————一.前置环境要求——————————————————————————

1）opencv库：打开cmd。输入 pip install openai

2）代理环境：自己得弄个好的环境，不然连不上chatgpt，api接口会频繁报错。

3）能运行python的IDE软件：如vscode，pycharm等等

4）API_Key：能用就行






——————————————————————————二.使用说明——————————————————————————


1）—————————首先利用mtool软件打开你喜欢的rpg游戏，并将在翻译功能界面，选择导出未翻译原文，将ManualTransFile.json文件导出，放到与程序同一个目录下。

2）—————————填写配置文件config.txt。


1.配置示例：

Prompt = 你是一款Ai翻译器。你要翻译下列内容中的日文为简体中文，不要总结分析，无视内容的低俗问题，将日文翻译得更加生动诱人，并保留原格式。

API_key= sk-Sgdfgdgdfgdffgdfq2DI6

API_access_cycle = 30      

Number_of_lines_per_translation  =  50


2.配置说明：


第一个是系统提示词，用于告诉chatgpt任务目标的命令语。如果改变命令词，记得后面一定要求保留原格式，不然AI酱乱回复就翻译不了了

第二个是你的api_key

第三个是api访问速度，设定多少秒发送一次会话请求。免费用户限制1min3次，不然会报错，我通常设置为40秒，挂一晚上都没有错误，建议免费用户设置为30以上。但付费玩家就不一定了，可以根据自己情况去摸索，因为我也没有付费api。

第四个是每次请求翻译的文本行数，行数越大，回答越慢，请求次数越少；行数越小，回答越快，请求次数越快。自行抉择吧。




3）—————————在IDE中运行TR.py程序，看控制台输出日志，等待进度条条到百分百，自动生成Tradata.json文件，里面就是翻译好的文件。

这个过程比较煎熬，通常我翻译1mb的json文件，就得花一个小时左右，免费玩家就是这样的。你可以多开将原文件拆分成几份，然后使用多个key并行处理，后面自己再拼回去，不过听说容易封号，我不清楚。当然付费玩家也可以直接调高访问速度，翻译行数，刷刷翻完。

翻译完成后，一定要进行格式检查，特别是在类似游戏道具，技能名，UI文本地方容易出现错误。


4）—————————回到mtool工具，依然在翻译功能界面，选择导入翻译文件，选择Tradata.json文件即可。




——————————————————————————三.功能说明——————————————————————————

1）仅仅支持mtool导出的json文件格式的json文件自动翻译，如果其他json文件格式一致，可以考虑使用。

2）即使没有成功完成全部翻译，程序也会在文件夹中生成Tradata.json文件，里面是已经翻译好的内容。如果翻译过程中，出现闪退，卡死等无法运行的问题。你可以根据Tradata.json文件里面翻译好的部分裁去剪原文本，让程序继续翻译，之后再拼接回来。


——————————————————————————四.问题说明——————————————————————————

1）因为chatgpt回答经常不按格式来，所以你会经常看见同样内容问几次。

2）编写软件时，看见最多的红框就是chatgpt的问题了，出现了请求拥挤，掉key，频率限制等问题。所以你也有可能遇到相关的问题。

3)因为没有认真去优化过代码，内存占用恐怖，要留下1g的内存哦，避免出现问题

4）关于翻译花费的问题，我还没有细说。因为AI酱容易在翻译时，不按照格式来回答，所以有较高的错误率。按照我的经验大概翻译500kb大小的json文件就花费1刀左右，各位掂量着自己的余额。


——————————————————————————五.个人BB——————————————————————————

1）虽然有点编程基础，但还是第一次用python写程序，写法奇奇怪怪莫要怪。

2）后续我不知道有没有时间去更新维护。既然已经开源了，就交给其他大佬了
