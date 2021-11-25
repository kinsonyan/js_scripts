安卓：晶彩天气(v8.3.7)

重新写了一下，支持领取几个定时宝箱和修复转发(不做分享阅读)
V2P重写订阅(包括了task):  https://raw.githubusercontent.com/leafxcy/JavaScript/main/jctq/jctq_rewrite_subscribe.json

注意单脚本不支持多账户，建议多容器跑。如果需要多账户在同一个脚本跑，请自行修改
脚本会自动提现，如果不想自动提现的，请不要捉提现body，或者新建环境变量jctqWithdrawFlag，写成0

重写：
https://tq.xunsl.com/v17/NewTask/getTaskListByWeather.json  -- 点开福利页即可获取jctqCookie，注意只支持单账户，新ck会覆盖旧ck
https://tq.xunsl.com/v5/CommonReward/toGetReward.json       -- 签到，观看签到翻倍视频，和福利页任务奖励（目前应该只有激励视频和20篇文章的奖励），获取完建议关掉重写
https://tq.xunsl.com/v5/article/info.json                   -- 点开文章获取文章body，获取完建议关掉重写
https://tq.xunsl.com/v5/article/detail.json                 -- 点开视频获取视频body，获取完建议关掉重写
https://tq.xunsl.com/v5/user/stay.json                      -- 阅读文章或者看视频一段时间后可以获取到时长body，获取完务必关掉重写
https://tq.xunsl.com/v5/nameless/adlickstart.json           -- 点开看看赚获取body，可以一直开着，脚本会自动删除重复和失效body
https://tq.xunsl.com/v5/Weather/giveBoxOnWeather.json       -- 点开福利页浮窗宝箱和观看翻倍视频获取body，获取完建议关掉重写
https://tq.xunsl.com/v5/weather/giveTimeInterval.json       -- 点开首页气泡红包和观看翻倍视频获取body，获取完建议关掉重写
https://tq.xunsl.com/v5/wechat/withdraw2.json               -- 提现一次对应金额获取body，新获取的提现body会覆盖旧的

任务：
jctq_daily.js   -- 每小时2到3次，领转发页定时宝箱，领福利页定时宝箱，领首页气泡红包，时段转发，刷福利视频，抽奖5次
jctq_kkz.js     -- 每天一到两次，完成看看赚任务，删除重复和失效的body
jctq_read.js    -- 每天一到两次，阅读文章，浏览视频
jctq_reward.js  -- 每天一次，放在其他脚本完成之后，签到和翻倍，任务奖励领取，统计今日收益，自动提现
