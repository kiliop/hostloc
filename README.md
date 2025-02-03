# Hostloc 刷分脚本
Hostloc 全球主机交流论坛 PHP刷分脚本okk

## 食用方法
1. 常规PHP环境
   1. 打开config.php，修改accounts部分的账号、密码和tg_push_key部分的推送key信息
   2. 使用定时任务，**每6小时**执行一次php文件。例：`0 */6 * * * php /home/www/index.php`
2. GitHub Actions
   1. Fork本项目到个人账号
   2. 找到项目顶部的Settings面板中左侧的Secrets and variables下的Actions板块
   3. 点击右侧的New repository secret按钮，增加如下两个参数，其中Secret中的值请按照相应格式替换成实际内容
      1. Name: LOC_ACCOUNTS, Secret: 账号1@@@密码1---账号2@@@密码2---账号3@@@密码3
      2. Name: TG_PUSH_KEY, Secret: 推送KEY
   4. 在项目顶部的Actions面板，开启Actions，然后找到Run index.php这一项，点击右侧**Enable workflow**按钮开启
   5. 默认会每6时执行一次，也可以手动点击**Run workflow**执行一次，查看下执行输出结果是否正常

## 消息推送 KEY
1. Telegram关注 @OnePushBot
2. 发送/start即可获取到你的推送KEY

## Log
- 2024-08-01 升级脚本，增加了GitHub Actions，同时调整为每6小时执行一次
- 2023-07-20 修复了下签到失败的消息推送功能
- 2021-09-29 最近好久没用也没管这个脚本了，跑去用Laravel写了个多账号带面板的签到，所以如果此脚本失效，记得喊我
- 2021-05-22 HTML版本受限于新版Chrome安全策略，已经失效。可以换其他垃圾浏览器试试，或者直接使用PHP版的
- 2021-03-01 临时更新，解决签到失败问题
- 2019-07-01 优化访问随机间隔时间，且每日多次尝试，~~晚上9点统一推送失败账号（**所以定时任务请设置每小时执行一次php脚本**）~~
- 2019-03-25 论坛偶尔防CC误伤，所以增加了签到(登录)失败的推送通知

## TODO
后面考虑做一个自动签到平台，问题用户放心把账号放我这吗？显然不会，再说吧

就这样溜了
